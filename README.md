gbraad's Dotfiles `dot` action
==============================

Use dotfiles' `dot`-command to start a self-contained dotfiles environment

### Usage

The runner needs to have at least `zsh` installed as a minimum. For this, run the following:

```yaml
      - name: Requiremnent for dot
        run: |
          sudo apt update
          sudo apt install -y zsh
```

or to ensure all requirements are in-place, use the `install-action` without changing the shell:

```yaml
      - name: Install dotfiles action
        uses: gbraad-dotfiles/install-action@v1
        with:
          change-shell: false
```

> [!NOTE]
> The `install-action` places the .dotfiles' files in the root of the `${USER}`'s `${HOME}`-folder.


After this, you can use the `dot-action` to run any .dotfiles' function

```yaml
      - name: Run dot command - devenv dotfedora exec cat /etc/os-release
        uses: gbraad-dotfiles/dot-action@main
        with:
          run: |
            devenv dotfedora exec cat /etc/os-release
```

Have a look here for an [example workflows](https://github.com/gbraad-dotfiles/actions-test/blob/main/.github/workflows/test-dot.yml).
