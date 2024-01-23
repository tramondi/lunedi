FROM archlinux:latest

RUN pacman -Syu --noconfirm

# LunarVim
RUN pacman -S --noconfirm make
RUN pacman -S --noconfirm gcc
RUN pacman -S --noconfirm git
RUN pacman -S --noconfirm ripgrep
RUN pacman -S --noconfirm fzf
RUN pacman -S --noconfirm ttf-jetbrains-mono-nerd
RUN pacman -S --noconfirm neovim
RUN LV_BRANCH='release-1.3/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.3/neovim-0.9/utils/installer/install.sh)
# ----

# go
RUN pacman -S --noconfirm go
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
ENV PATH="$PATH:/root/go/bin"
