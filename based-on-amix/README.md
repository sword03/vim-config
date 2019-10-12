# Install

- Cover the configuration file

    ```
    cp -rf ./my_configs.vim ~/.vim_runtime/
    ```

- Install [yapf](https://github.com/google/yapf.git)

    ```
    cd ~/.vim_runtime
    git clone https://github.com/google/yapf.git my_plugins/yapf
    ```
    Add key mappings to file ~/.vim_runtime/my_configs.vim
    ```
     :nnoremap <leader>y :call Yapf()<cr>
    ```


