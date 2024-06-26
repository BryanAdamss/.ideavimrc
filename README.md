# .ideavimrc
My IdeaVim conf base on [https://github.com/JetBrains/ideavim/discussions/303#discussioncomment-7664118](https://github.com/JetBrains/ideavim/discussions/303#discussioncomment-7664118)


```
" .ideavimrc is a configuration file for IdeaVim plugin. It uses
"   the same commands as the original .vimrc configuration.
" You can find a list of commands here: https://jb.gg/h38q75
" Find more examples here: https://jb.gg/share-ideavimrc
" --- Enable IdeaVim plugins https://jb.gg/ideavim-plugins
"" -- Map IDE actions to IdeaVim -- https://jb.gg/abva4t
"" Map \r to the Reformat Code action
"map \r <Action>(ReformatCode

"" Map <leader>d to start debug
"map <leader>d <Action>(Debug)

"" Map \b to toggle the breakpoint on the current line
"map \b <Action>(ToggleLineBreakpoint)

" 参考：https://github.com/JetBrains/ideavim/discussions/303#discussioncomment-7664118
" vim settings
" 设置你的视图或窗口中顶部和底部的“保留”行数为5行
set scrolloff=5
" 历史记录条数
set history=1000
" Do incremental searching.-增量搜索,在搜索模式下输入字符时，Vim 将会立即跳转到文档中第一个符合你所输入的内容的位置
set incsearch

" Don't use Ex mode, use Q for formatting.
" 不用Q进入Ex模式，而是用来做格式化
map Q gq

" status bar
set showmode

" leader
map <space> <nop>
let mapleader="\<space>"

" find and replace
set hlsearch
set incsearch
set ignorecase
set smartcase
set gdefault
nmap <leader>nh :noh<CR>

" ideavim settings
set ideajoin
set ideamarks
set idearefactormode=normal
set ideastatusicon=gray

" better HJKL
map H ^
map L $
map J }
map K {

" better escape
imap jk <Esc>

" location
nmap <C-i> <Action>(Back)
nmap <C-o> <Action>(Forward)

" buffer (buffer < window < tab)
nmap <leader>xx <Action>(CloseContent)
nmap <leader>xa <Action>(CloseAllEditors)
nmap <leader>xo <Action>(CloseAllEditorsButActive)
nmap <leader>xp <Action>(CloseAllUnpinnedEditors)

" window
nmap <C-Tab> <Action>(PreviousTab)
nmap <Tab> <Action>(NextTab)
nmap <leader>p <Action>(PinActiveEditorTab)

nmap <leader>1 <Action>(GoToTab1)
nmap <leader>2 <Action>(GoToTab2)
nmap <leader>3 <Action>(GoToTab3)
nmap <leader>4 <Action>(GoToTab4)
nmap <leader>5 <Action>(GoToTab5)
nmap <leader>6 <Action>(GoToTab6)
nmap <leader>7 <Action>(GoToTab7)
nmap <leader>8 <Action>(GoToTab8)
nmap <leader>9 <Action>(GoToTab9)

" tab
map <leader>sh <Action>(MoveTabLeft)
map <leader>sj <Action>(MoveTabDown)
map <leader>sk <Action>(MoveTabUp)
map <leader>sl <Action>(MoveTabRight)
map <leader>sH <Action>(SplitHorizontally)
map <leader>sV <Action>(SplitVertically)

nmap <C-p> <Action>(JumpToLastWindow)
nmap <M-i> <Action>(PrevSplitter)
nmap <M-o> <Action>(NextSplitter)
nmap <C-k> <C-w>k
nmap <C-j> <C-w>j
nmap <C-h> <C-w>h
nmap <C-l> <C-w>l

nmap <leader>ww <Action>(HideAllWindows)
nmap <leader>wk <Action>(StretchSplitToTop)
nmap <leader>wj <Action>(StretchSplitToBottom)
nmap <leader>wh <Action>(StretchSplitToLeft)
nmap <leader>wl <Action>(StretchSplitToRight)
nmap <leader>wm <Action>(MaximizeEditorInSplit)
nmap <leader>wu <Action>(UnsplitAll)

" menu
nmap <leader>mm <Action>(MainMenu)
nmap <leader>ma <Action>(AnalyzeMenu)
nmap <leader>mb <Action>(BuildMenu)
nmap <leader>mc <Action>(CodeMenu)
nmap <leader>mf <Action>(FindMenuGroup)
nmap <leader>mg <Action>(GoToMenu)
nmap <leader>ms <Action>(ScopeViewPopupMenu)
nmap <leader>mt <Action>(EditorTabPopupMenu)
nmap <leader>mw <Action>(ToolWindowsGroup)

" file
nmap <leader>of <Action>(OpenFile)
nmap <leader>yp <Action>(CopyAbsolutePath)
nmap <leader>rf <Action>(RecentFiles)
nmap <leader>rl <Action>(RecentLocations)
nmap <leader>rp <Action>(ManageRecentProjects)
nmap <leader>sh <Action>(LocalHistory.ShowHistory)
nmap <leader>sf <Action>(ShowFilePath)
nmap <leader>si <Action>(SelectIn)
nmap <leader>fp <Action>(FindInPath)
nmap <leader>rp <Action>(ReplaceInPath)
nmap <leader>sw <Action>($SearchWeb)

" tag
nmap <leader>fu <Action>(FindUsages)
nmap <leader>fs <Action>(FileStructurePopup)
nmap <leader>su <Action>(ShowUsages)
nmap <leader>hl <Action>(HighlightUsagesInFile)
nmap <leader>qp <Action>(QuickPreview)
nmap <leader>qd <Action>(QuickDefinition)
nmap <leader>qD <Action>(QuickTypeDefinition)

" code
map <leader>c <Action>(CommentByLineComment)
map <leader>C <Action>(CommentByBlockComment)
nmap <leader>qf <Action>(ShowIntentionActions)
nmap <leader>se <Action>(ShowErrorDescription)
nmap <leader>om <Action>(OverrideMethods)
nmap <leader>im <Action>(ImplementMethods)
nmap <leader>fc <Action>(ReformatCode)
nmap <leader>ic <Action>(InspectCode)
nmap <leader>so <Action>(SelectAllOccurrences)
nmap <leader>gc <Action>(Generate)
nmap <leader>gt <Action>(GoToTest)

" run
nmap <leader>rc <Action>(ContextRun)
nmap <leader>rx <Action>(chooseRunConfiguration)
nmap <leader>rr <Action>(Rerun)
nmap <leader>rt <Action>(RunTests)
nmap <leader>rs <Action>(Stop)

" debug
nmap <leader>dc <Action>(ContextDebug)
nmap <leader>dx <Action>(Debug)
nmap <leader>db <Action>(ToggleLineBreakpoint)
nmap <leader>de <Action>(EditBreakpoint)
nmap <leader>dv <Action>(ViewBreakpoints)

" build
nmap <leader>bb <Action>(BuildMenu)

" refactor
nmap <leader>rn <Action>(RenameElement)
nmap <leader>re <Action>(Refactorings.QuickListPopupAction)
nmap <leader>uw <Action>(Unwrap)
nmap <leader>sw <Action>(SurroundWith)
nmap <leader>sd <Action>(SafeDelete)
nmap <leader>oi <Action>(OptimizeImports)

" hierarchy
nmap <leader>hc <Action>(CallHierarchy)
nmap <leader>hm <Action>(MethodHierarchy)
nmap <leader>ht <Action>(TypeHierarchy)

" collapse
nmap zz <Action>(ExpandCollapseToggleAction)
nmap za <Action>(CollapseAllRegions)
nmap zA <Action>(ExpandAllRegions)

" zen
nmap <leader>z <Action>(ToggleZenMode)

" []
nmap [b <Action>(PreviousTab)
nmap ]b <Action>(NextTab)
nmap [g <Action>(GotoPreviousError)
nmap ]g <Action>(GotoNextError)
nmap [u <Action>(GotoPrevElementUnderCaretUsage)
nmap ]u <Action>(GotoNextElementUnderCaretUsage)
nmap [o <Action>(PreviousOccurence)
nmap ]o <Action>(NextOccurence)
nmap [m <Action>(MethodUp)
nmap ]m <Action>(MethodDown)
nmap [c <Action>(JumpToLastChange)
nmap ]c <Action>(JumpToNextChange)

" goto
nmap <leader>a <Action>(GotoAction)
nmap ga <Action>(GotoAction)
nmap gc <Action>(GotoClass)
nmap gf <Action>(GotoFile)
nmap gs <Action>(GotoSymbol)
nmap gt <Action>(GoToTest)
nmap gT <Action>(TextSearchAction)
nmap go <Action>(GotoSuperMethod)
nmap gd <Action>(GotoDeclaration)
nmap gD <Action>(GotoTypeDeclaration)
nmap gi <Action>(GotoImplementation)
nmap gI <Action>(QuickImplementations)
nmap gn <Action>(ShowNavBar)

" terminal
nmap <leader>tt <Action>(ActivateTerminalToolWindow)
nmap <leader>tc <Action>(Terminal.OpenInTerminal)

" bookmark
nmap mm <Action>(ToggleBookmark)
nmap ms <Action>(ShowBookmarks)

" todo
nmap <leader>to <Action>(ActivateTODOToolWindow)

" task
nmap <leader>ts <Action>(tasks.goto)

" idea join
nmap \\jl <Action>(EditorJoinLines)

" gist
nmap \\cg <Action>(Github.Create.Gist)

" vcs
nmap <leader>v <Action>(VcsGroups)

" open IdeaVim settings
nmap \\v <Action>(VimActions)

" continuous shift
xnoremap < <gv
xnoremap > >gv

" alias
" ctrl+a 全选复制
nmap <C-a> ggVG"+y

" 插件相关
" text-object (bundle plugin)
Plug 'dbakker/vim-paragraph-motion'
Plug 'michaeljsmith/vim-indent-object'
Plug 'kana/vim-textobj-entire'
Plug 'vim-scripts/argtextobj.vim'

" jump-motion (required idea plugin: IdeaVim-EasyMotion, AceJump)
" 需要额外安装IdeaVim-EasyMotion, AceJump插件，使用<leader><leader>w快速跳转
Plug 'easymotion/vim-easymotion'

" sneak(bundle plugin)-使用s{char}{char}搜索
Plug 'justinmk/vim-sneak'

" highlight yank (bundle plugin)-高亮拷贝的文本
Plug 'machakann/vim-highlightedyank'
let g:highlightedyank_highlight_duration = "1000"

" Commentary(bundle plugin)-用gc gcc 实现注释
Plug 'tpope/vim-commentary'

" multiple (bundle plugin)-多光标编辑
Plug 'terryma/vim-multiple-cursors'

" translation (required idea plugin: Translation)
" 翻译，需要在Marketplace额外安装Translation插件
" nmap \\tt <Action>($ShowTranslationDialogAction)
" nmap \\ts <Action>($TranslateTextComponent)
" nmap \\ti <Action>($InclusiveTranslateAction)
" nmap \\te <Action>($ExclusiveTranslateAction)

" string manipulate (required idea plugin: String Manipulation)
" 字符串快捷操作-需要在Marketplace额外安装string manipulation插件
nmap <leader>ss <Action>(osmedile.intellij.stringmanip.PopupChoiceAction)

" code screenshot (required idea plugin: Code Screenshots)
" 代码截图，需要在Marketplace额外安装Code Screenshots插件
" nmap <leader>cs <Action>(one.util.ideaplugin.screenshoter.CopyImageAction)

" surround (bundle plugin)
" usage: https://github.com/tpope/vim-surround
Plug 'tpope/vim-surround'

" exchange (bundle plugin)
" usage: https://github.com/tommcdo/vim-exchange
Plug 'tommcdo/vim-exchange'

" nerdtree (bundle plugin)
Plug 'preservim/nerdtree'

" replace with register (bundle plugin)
" usage: https://github.com/vim-scripts/ReplaceWithRegister
Plug 'vim-scripts/ReplaceWithRegister'


```
