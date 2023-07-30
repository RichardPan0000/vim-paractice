"" Source your .vimrc
"source ~/.vimrc
"============================================================"
"= Extentions"
"============================================================"
Plug 'tpope/vim-surround'
Plug 'preservim/nerdtree'



"==================================================="
"=Basic settings"
"==================================================="
"" -- Suggested options --
" Show a few lines of context around the cursor. Note that this makes the
" text scroll if you mouse-click near the start or end of the window.
"set scrolloff=5"
set scrolloff=30
set clipboard+=unnamed
set ignorecase

set number
set relativenumber

set incsearch
set hlsearch
set keep-english-in-normal


" Do incremental searching.
set incsearch

" Don't use Ex mode, use Q for formatting.
map Q gq


"" -- Map IDE actions to IdeaVim -- https://jb.gg/abva4t
"" Map \r to the Reformat Code action
"map \r <Action>(ReformatCode)

"" Map <leader>d to start debug
"map <leader>d <Action>(Debug)

"" Map \b to toggle the breakpoint on the current line
"map \b <Action>(ToggleLineBreakpoint)


" Find more examples here: https://jb.gg/share-ideavimrc

" ========================================================="
" = No Leader Keymaps===================================="
" ========================================================="
nmap ge <action>(GotoNextError)
nmap gt <action>(GotoTest)


" 设置easymotion  surround multiple-cursors 比较好"
set ideamarks
set easymotion
set surround
set argtextobj
set multiple-cursors


"==========================================================================="
"= Leader Keymaps==========================================================="
"==========================================================================="
" leaderkey 设置leaderkey是空格比较好
let mapleader=" "

" ================================================================================================
" = Extensions =====================================
" ================================================================================================
Plug 'tpope/vim-surround'
Plug 'preservim/nerdtree'
Plug 'terryma/vim-multiple-cursors'
map mc <A-n>
map mx <A-x>
map mv <A-p>


" ================================================================================================
" = Basic settings =====================================
" ================================================================================================
set clipboard+=unnamed
set ignorecase
set scrolloff=30
set history=200

set number
set relativenumber

set incsearch
set hlsearch
set keep-english-in-normal

" ================================================================================================
" = No Leader Keymaps =====================================
" ================================================================================================
nmap ge <action>(GotoNextError)
nmap gt <action>(GotoTest)
nmap gm <action>(MethodUp)
" last changed in current buffer(file)
nmap ga <action>(GotoImplementation)

set exchange
set highlightedyank
set textobj-entire
set keep-english-in-normal-and-restore-in-insert
set NERDTree
set ReplaceWithRegister


"在insert模式下进行退出，jk直接映射为esc，"
inoremap jk <esc>
" nerdtre
map <leader>e :action SelectInProjectView<CR>
nnoremap <leader>d :NERDTreeFocus<CR>


" bookmark
nmap ma <action>(ToggleBookmark)

nmap L <action>(NextTab)
nmap H <action>(PreviousTab)


" ================================================================================================
" = Leader Keymaps =====================================
" ================================================================================================
" leaderkey
let mapleader=" "

" ================================================================================================
" 👻👻👻 Which-Key 👻👻👻
" ================================================================================================
set which-key
set notimeout

" d: diff
nmap <leader>dd <action>(Vcs.ShowTabbedFileHistory)

" f: Find/Format ⭐️
let g:WhichKeyDesc_FindOrFormat = "<leader>f FindOrFormat"
let g:WhichKeyDesc_FindOrFormat_FindFile = "<leader>ff FindFile"
nmap <leader>ff <action>(GotoFile)

let g:WhichKeyDesc_FindOrFormat_FindFileLocation = "<leader>fl FindFileLocation"
nmap <leader>fl <action>(SelectInProjectView)

let g:WhichKeyDesc_FindOrFormat_FindText = "<leader>ft FindText"
nmap <leader>ft <action>(FindInPath)

let g:WhichKeyDesc_FindOrFormat_Commands = "<leader>fc Commands"
nmap <leader>fc <action>(GotoAction)

let g:WhichKeyDesc_FindOrFormat_OpenedProject = "<leader>fp OpenedProject"
nmap <leader>fp <action>(OpenProjectWindows)

let g:WhichKeyDesc_FindOrFormat_Format = "<leader>fm Format"
nmap <leader>fm <action>(ReformatCode) \| <action>(OptimizeImports)

" g: Git ⭐️
let g:WhichKeyDesc_Git = "<leader>g Git"
let g:WhichKeyDesc_Git_RollbackHunk = "<leader>gr RollbackHunk"
nmap <leader>gr :action Vcs.RollbackChangedLines<CR>

" i: Insert ⭐️
let g:WhichKeyDesc_InsertAfterBrackets = "<leader>i InsertAfterBrackets"
nmap <leader>i f(a

" j: add Semicolon and goto nextline⭐️
let g:WhichKeyDesc_InsertSemicolon = "<leader>j InsertSemicolon"
nmap <leader>j A;<ESC>o

" l: lsp: Language server protocol (align with neovim)⭐️
let g:WhichKeyDesc_LSP = "<leader>l LSP"
let g:WhichKeyDesc_LSP_Rename = "<leader>lr Rename"
nmap <leader>lr <action>(RenameElement)


" n: No ⭐️
let g:WhichKeyDesc_No_Highlight = "<leader>nl NoHighlight"
nmap <leader>nl :nohlsearch<CR>


" s: Show ⭐️
let g:WhichKeyDesc_Show = "<leader>s Show"
let g:WhichKeyDesc_Show_FileStructure = "<leader>ss ShowFileStructure"
nmap <leader>ss <action>(FileStructurePopup)
let g:WhichKeyDesc_Show_Bookmarks = "<leader>sb ShowBookmarks"
nmap <leader>sb <action>(ShowBookmarks)
let g:WhichKeyDesc_Show_ParameterInfo = "<leader>sb ShowParameterInfo"
nmap <leader>sp <action>(ParameterInfo)

" r: Run/Re ⭐️
let g:WhichKeyDesc_RunOrRe = "<leader>r RunOrRe"
let g:WhichKeyDesc_RunOrRe_ReRun = "<leader>rr ReRun"
nmap <leader>rr <action>(Rerun)
let g:WhichKeyDesc_RunOrRe_ReRunTests = "<leader>rt ReRunTests"
nmap <leader>rt <action>(RerunTests)
let g:WhichKeyDesc_RunOrRe_Rename = "<leader>rn Rename"
map <leader>rn <action>(RenameElement)

" w: Window ⭐️
let g:WhichKeyDesc_Windows = "<leader>w Windows"
let g:WhichKeyDesc_Windows_maximize = "<leader>wo maximize"
nmap <leader>wo <action>(UnsplitAll) \| <action>(HideAllWindows)
let g:WhichKeyDesc_Windows_splitWindowVertically = "<leader>wl splitWindowVertically"
nmap <leader>wl <action>(Macro.SplitVertically)
let g:WhichKeyDesc_Windows_closeActiveWindow = "<leader>wc closeActiveWindow"
nmap <leader>wc <c-w>c

" z: zip(fold) ⭐️
let g:WhichKeyDesc_Zip = "<leader>z Zip"
let g:WhichKeyDesc_Zip_unZipAll = "<leader>zo unZipAll"
nmap <leader>zo <action>(ExpandAllRegions)
let g:WhichKeyDesc_Zip_ZipAll = "<leader>zc ZipAll"
nmap <leader>zc <action>(CollapseAllRegions)

" c: Close ⭐️;
let g:WhichKeyDesc_CloseBuffer = "<leader>c CloseBuffer"
nmap <leader>c :q!<CR>

" e: Toggle Explorer ⭐️
let g:WhichKeyDesc_ToggleExplorerOrExtract = "<leader>e ToggleExplorer"
nmap <leader>e <action>(ActivateProjectToolWindow)
" e: Extract
" extract method/function
vmap <leader>em <action>(ExtractMethod)
" extract constant
vmap <leader>ec <action>(IntroduceConstant)
" extract field
vmap <leader>ef <action>(IntroduceField)
" extract variable
vmap <leader>ev <action>(IntroduceVariable)



""" Idea specific settings ------------------
set ideajoin
set idearefactormode=keep

" clear the highlighted search result
nnoremap <Leader>sc :nohlsearch<CR>

" easymotion
map <leader>f <Plug>(easymotion-s)


" Window operation

nnoremap <leader>ww <C-W>w
nnoremap <leader>wd <C-W>c
nnoremap <leader>wj <C-W>j
nnoremap <leader>wk <C-W>k
nnoremap <leader>wh <C-W>h
nnoremap <leader>wl <C-W>l
nnoremap <leader>ws <C-W>s
nnoremap <leader>w- <C-W>s
noremap <leader>wv <C-W>v
nnoremap <leader>w\| <C-W>v



" copy and paste
noremap <Leader>y "*y
noremap <Leader>p "*p
noremap <Leader>P "0p
vnoremap Y "+y


" Tab operation
nnoremap tn gt
nnoremap tp gT


" Insert mode shortcut
inoremap <C-h> <Left>
inoremap <C-j> <Down>
inoremap <C-k> <Up>
inoremap <C-l> <Right>
inoremap <C-a> <Home>
inoremap <C-e> <End>
inoremap <C-d> <Delete>
" Quit normal mode
nnoremap <Space>q  :action CloseProject<CR>
nnoremap <Space>Q  :qa!<CR>


" intellij built in key map

nnoremap <leader>a :action GotoAction<CR>
nnoremap <leader>b :action Bookmarks<CR>
nnoremap <leader>c :action GotoClass<CR>
"nnoremap <leader>e :action SearchEverywhere<CR>
"nnoremap <leader>f :action FindInPath<CR>
nnoremap <leader>gc :action Git.CompareWithBranch<CR>
nnoremap <leader>ga :action Annotate<CR>
nnoremap <leader>gh :action Vcs.ShowTabbedFileHistory<CR>
nnoremap <leader>nj :action NewClass<CR>
nnoremap <leader>nt :action Kotlin.NewFile<CR>
nnoremap <leader>r :action RecentFiles<CR>

" build and compile code
nnoremap <leader>mr :action Maven.Reimport<CR>

"toggle something
"toggle track vim action Id
nnoremap ta :action VimFindActionIdAction<CR>

" run and debug
nnoremap ,d :action Debug<CR>
nnoremap ,r :action Run<CR>
nnoremap ,c :action CompileDirty<CR>
nnoremap ,b :action ToggleLineBreakpoint<CR>
nnoremap ,v :action ViewBreakpoints<CR>
nnoremap ,s :action Stop<CR>
" navigation
nnoremap gs :action GotoSuperMethod<CR>
nnoremap gb :action JumpToLastChange<CR>
nnoremap gi :action GotoImplementation<CR>
nnoremap gd :action GotoDeclaration<CR>
nnoremap gf :action FileStructurePopup<CR>

" code actions
nnoremap U :action FindUsages<CR>
nnoremap R :action RenameElement<CR>
nnoremap == :action ReformatCode<CR>
vnoremap = :action ReformatCode<CR>
nnoremap -- :action OptimizeImports<CR>
nnoremap cc :action CommentByLineComment<CR>
vnoremap cc :action CommentByLineComment<CR>



" 将leader键设置为,
let mapleader=','
let g:mapleader=','

nnoremap <leader>n :NERDTreeFocus<CR>
nnoremap <leader>m :NERDTree<CR>
nnoremap <leader>t :NERDTreeToggle<CR>
nnoremap <leader>f :NERDTreeFind<CR>
