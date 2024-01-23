FROM archlinux:latest

RUN pacman -Sy

# LunarVim
RUN pacman -S neovim git make ripgrep fzf ttf-jetbrains-mono-nerd --noconfirm
RUN LV_BRANCH='release-1.3/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.3/neovim-0.9/utils/installer/install.sh)
# ----

# go
RUN pacman -S go --noconfirm
RUN go install golang.org/x/tools/gopls@latest
RUN go install github.com/nametake/golangci-lint-langserver@latest
RUN go install github.com/golangci/golangci-lint/cmd/golangci-lint@latest
RUN go install github.com/josharian/impl@latest
# RUN go get -u github.com/cweill/gotests/...
RUN go install github.com/fatih/gomodifytags@latest
RUN go install mvdan.cc/gofumpt@latest
RUN go install golang.org/x/tools/cmd/goimports@latest
# ----

ENV PATH="$PATH:/root/.local/bin"

