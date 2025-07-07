gbraad's Dotfiles `dot` action
==============================

Use dotfiles' `dot`-command to start a self-contained dotfiles environment

### Usage

```yaml
      - name: Requiremnent for dot
        run: |
          sudo apt update
          sudo apt install -y zsh

      - name: Run dot command - devenv dotfedora exec cat /etc/os-release
        uses: gbraad-dotfiles/dot-action@main
        with:
          run: |
            devenv dotfedora exec cat /etc/os-release
```

Have a look here for an [example workflows](https://github.com/gbraad-dotfiles/actions-test/blob/main/.github/workflows/test-dot.yml).
