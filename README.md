# vim-wrangler

The wrangler plugin for Vim.
Based on  Pawel 'kTT' Salata <rockplayer.pl@gmail.com> vimerl wrangler branch 
(https://github.com/jimenezrick/vimerl/tree/wrangler-support).

## Configuration

Add the following lines to your vimrc file:

    "enable wrangler
    let g:erlangRefactoring = 1

    "set path to wrangler directory
    let g:erlangWranglerPath = '/Users/pawel.pikula/dev/other/wrangler'

    "sample wrangler bindings
    nnoremap <leader>e :call ErlangExtractFunction("n")<ENTER>
    vnoremap <leader>e :call ErlangExtractFunction("v")<ENTER>
    noremap  <leader>m :call ErlangRenameModule()<ENTER>
    noremap  <leader>f :call ErlangRenameFunction()<ENTER>
    noremap  <leader>v :call ErlangRenameVariable()<ENTER>
    noremap  <leader>p :call ErlangRenameProcess()<ENTER>
    noremap  <leader>u :call ErlangUndo()<ENTER>

## Troubleshooting

### (ZSH) The plugin uses incorrect version of Erlang.
In my case it prefered brew installation over the kerl one. It appeared that
MacVim was using wrong PATH variable. If you using zsh and have similar issue try
the following:

    $ sudo mv /etc/zshenv /etc/zprofile

NOTE: If the system already has a `/etc/zprofile`,
make sure you merge the two files instead of overwriting `/etc/zprofile`.

source:
https://github.com/b4winckler/macvim/wiki/Troubleshooting#rename-the-etczshenv-file-to-etczprofile

## ToDo

- [x] automatically find erl_call
- [x] discover if the current file is inside `apps/*/src` directory if so pass all apps to wrangler's search path
- [ ] create more generic function that will allow to easily bind every wrangler command
- [ ] vim documentation

