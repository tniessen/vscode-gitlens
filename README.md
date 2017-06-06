[![](https://vsmarketplacebadge.apphb.com/version/eamodio.gitlens.svg)](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
[![](https://vsmarketplacebadge.apphb.com/installs/eamodio.gitlens.svg)](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
[![](https://vsmarketplacebadge.apphb.com/rating/eamodio.gitlens.svg)](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
[![Chat at https://gitter.im/vscode-gitlens/Lobby](https://badges.gitter.im/vscode-gitlens/Lobby.svg)](https://gitter.im/vscode-gitlens/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# GitLens

GitLens **supercharges** the built-in Visual Studio Code Git capabilities. It helps you to **visualize code authorship** at a glance via Git blame annotations and code lens, **seamlessly navigate and explore** the history of a file or branch, **gain valuable insights** via powerful comparision commands, and so much more.

GitLens provides an unobtrusive blame annotation at the end of the current line, a status bar item showing the commit information (author and date, by default) of the current line, code lens showing the most recent commit and # of authors of the file and/or code block, and many commands for exploring commits and histories, comparing and navigating revisions, stash access, repository status, and more. GitLens is also [highly customizable](#extension-settings) to meet your specific needs — find code lens intrusive or the current line blame annotation distracting — no problem, it is easy to [turn them off or change how they behave](#extension-settings).

## Previews
#### Featuring code lens, file blame annotations, and navigation and exploration via quick pick menus
![GitLens preview 1](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/gitlens-preview1.gif)

#### Featuring current line blame annotation and hovers, status bar commit details, quick pick menus, compare with previous, and more
![GitLens preview 2](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/gitlens-preview2.gif)

## Features

#### Git Blame Annotations

- Adds an unobtrusive, highly [customizable](#line-blame-annotation-settings) and [themeable](#theme-settings), **Git blame annotation** to the end of the current line ([optional](#line-blame-annotation-settings), on by default)

  ![Line Blame Annotation](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/screenshot-line-blame-annotations.png)
  - Contains the author, date, and message of the line's most recent commit, by [default](#line-blame-annotation-settings)
  - Also adds a `details` hover annotation to the current line annotation which provides more commit details ([optional](#line-blame-annotation-settings), on by default)
  - Also adds a `changes` (diff) hover annotation to the current line annotation which provides **instant** access to the line's previous version ([optional](#line-blame-annotation-settings), on by default)

- Adds on-demand, beautiful, highly [customizable](#file-blame-annotation-settings) and [themeable](#theme-settings), **Git blame annotations** of the whole file

  ![File Blame Annotation](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/screenshot-file-blame-annotations.png)
  - Choose between `gutter` (default) and `hover` [annotation styles](#file-blame-annotation-settings)
  - Contains the commit message and date, by [default](#file-blame-annotation-settings)
  - Also adds a `details` hover annotation to the line's annotation which provides more commit details ([optional](#file-blame-annotation-settings), on by default)

- Adds [customizable](#status-bar-settings) **blame information** about the current line to the **status bar**  ([optional](#status-bar-settings), on by default)

  ![Status Bar Blame](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/screenshot-status-bar.png)
  - Contains the commit author and date, by [default](#status-bar-settings)
  - Clicking the status bar item will, by [default](#status-bar-settings), show a **commit details quick pick menu** with commands for comparing, navigating and exploring commits, and more
  - Provides [customizable](#status-bar-settings) click behavior — choose between one of the following
    - Toggle file blame annotations on and off
    - Toggle code lens on and off
    - Compare the line commit with the previous commit
    - Compare the line commit with the working tree
    - Show a quick pick menu with details and commands for the commit (default)
    - Show a quick pick menu with file details and commands for the commit
    - Show a quick pick menu with the commit history of the file
    - Show a quick pick menu with the commit history of the current branch

- Adds a `Toggle File Blame Annotations` command (`gitlens.toggleFileBlame`) with a shortcut of `alt+b` to toggle the file blame annotations on and off
  - Also adds a `Show File Blame Annotations` command (`gitlens.showFileBlame`)

- Adds a `Toggle Line Blame Annotations` command (`gitlens.toggleLineBlame`) to toggle the current line blame annotations on and off
  - Also adds a `Show Line Blame Annotations` command (`gitlens.showLineBlame`)

#### Git Code Lens

- Adds **code lens** to the top of the file and on code blocks ([optional](#code-lens-settings), on by default)

  ![Git Code Lens](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/develop/images/screenshot-code-lens.png)
  - **Recent Change** — author and date of the most recent commit for the file or code block
    - Clicking the code lens will, by [default](#code-lens-settings), show a **commit file details quick pick menu** with commands for comparing, navigating and exploring commits, and more
  - **Authors** — number of authors of the file or code block and the most prominent author (if there is more than one)
    - Clicking the code lens will, by [default](#code-lens-settings), toggle the file Git blame annotations on and off of the whole file
    - Will be hidden if the author of the most recent commit is also the only author of the file or block, to avoid duplicate information and reduce visual noise

- Provides [customizable](#code-lens-settings) click behavior for each code lens — choose between one of the following
  - Toggle file blame annotations on and off
  - Compare the commit with the previous commit
  - Show a quick pick menu with details and commands for the commit
  - Show a quick pick menu with file details and commands for the commit
  - Show a quick pick menu with the commit history of the file
  - Show a quick pick menu with the commit history of the current branch

- Adds a `Toggle Git Code Lens` command (`gitlens.toggleCodeLens`) with a shortcut of `shift+alt+b` to toggle the code lens on and off

#### Powerful Comparison Tools

- Effortlessly navigate between comparisions via the `alt+,` and `alt+.` shortcut keys to go back and forth through a file's revisions

- Provides easy access to the following comparison commands via the `Command Palette` as well as in context via the many provided quick pick menus

- Adds a `Directory Compare` command (`gitlens.diffDirectory`) to open the configured Git difftool to compare directories between branches

- Adds a `Compare File with...` command (`gitlens.diffWithBranch`) to compare the active file with the same file on the selected branch

- Adds a `Compare File with Next Commit` command (`gitlens.diffWithNext`) with a shortcut of `alt+.` to compare the active file/diff with the next commit revision

- Adds a `Compare File with Previous` command (`gitlens.diffWithPrevious`) with a shortcut of `alt+,` to compare the active file/diff with the previous commit revision

- Adds a `Compare Line Commit with Previous` command (`gitlens.diffLineWithPrevious`) with a shortcut of `shift+alt+,` to compare the active file/diff with the previous line commit revision

- Adds a `Compare File with Working Tree` command (`gitlens.diffWithWorking`) with a shortcut of `shift+alt+w` to compare the most recent commit revision of the active file/diff with the working tree

- Adds a `Compare Line Commit with Working Tree` command (`gitlens.diffLineWithWorking`) with a shortcut of `alt+w` to compare the commit revision of the active line with the working tree

#### Navigate and Explore

- Adds a `Search Commits` command (`gitlens.showCommitSearch`) with a shortcut of `alt+/` to search for commits by message, author, file(s), or commit id

- Adds commands to open files, commits, branches, and the repository in the supported remote services, currently **BitBucket, GitHub, GitLab, and Visual Studio Team Services** — only available if a Git upstream service is configured in the repository
  - `Open Branch in Remote` command (`gitlens.openBranchInRemote`) — opens the current branch commits in the supported remote service
  - `Open Line Commit in Remote` command (`gitlens.openCommitInRemote`) — opens the commit revision of the active line in the supported remote service
  - `Open File in Remote` command (`gitlens.openFileInRemote`) — opens the active file/revision in the supported remote service
  - `Open Repository in Remote` command (`gitlens.openRepoInRemote`) — opens the repository in the supported remote service

- Adds a `Show Current Branch History` command (`gitlens.showQuickRepoHistory`) with a shortcut of `shift+alt+h` to show a paged **branch history quick pick menu** of the current branch for exploring its commit history

  ![Branch History Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-branch-history.png)

  - Provides entries to `Show Commit Search` and `Open Branch in <remote-service>` when available
  - Navigate back to the previous quick pick menu via `alt+left arrow`, if available
  - Navigate pages via `alt+,` and `alt+.` to go backward and forward respectively

- Adds a `Show Branch History` command (`gitlens.showQuickBranchHistory`) to show a paged **branch history quick pick menu** of the selected branch for exploring its commit history
  - Provides the same features as `Show Current Branch History` above

- Adds a `Show File History` command (`gitlens.showQuickFileHistory`) to show a paged **file history quick pick menu** of the active file for exploring its commit history

  ![File History Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-file-history.png)

  - Provides entries to `Show Branch History` and `Open File in <remote-service>` when available
  - Navigate back to the previous quick pick menu via `alt+left arrow`, if available
  - Navigate pages via `alt+,` and `alt+.` to go backward and forward respectively

- Adds a `Show Commit Details` command (`gitlens.showQuickCommitDetails`) to show a **commit details quick pick menu** of the most recent commit of the active file

  ![Commit Details Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-commit-details.png)

  - Quickly see the set of files changed in the commit, complete with status indicators for adds, changes, renames, and deletes
  - Provides entries to `Copy to Clipboard`, `Directory Compare`, `Open Changed Files`, `Open File in <remote-service>` when available, and more
  - Navigate back to the previous quick pick menu via `alt+left arrow`, if available
  - Use the `alt+right arrow` shortcut on an entry to execute it without closing the quick pick menu, if possible — commands that open windows outside of VS Code will still close the quick pick menu unless [`"gitlens.advanced.quickPick.closeOnFocusOut": false`](#extension-settings) is set
  - Use the `alt+right arrow` shortcut on a file entry in the `Changed Files` section to preview the current revision of the while leaving the quick pick menu open
    - NOTE: Once [vscode issue #10568](https://github.com/Microsoft/vscode/issues/10568) is resolved this will change to preview the comparison of the current revision with the previous one

- Adds a `Show Line Commit Details` command (`gitlens.showQuickCommitFileDetails`) with a shortcut of `alt+c` to show a **file commit details quick pick menu** of the most recent commit of the active file

  ![Line Commit Details Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-commit-file-details.png)

  - Provides entries to `Show Commit Details`, `Show File History`, `Compare File with...`, `Copy to Clipboard`, `Open File`, `Open File in <remote-service>` when available, and more
  - Navigate back to the previous quick pick menu via `alt+left arrow`, if available
  - Use the `alt+right arrow` shortcut on an entry to execute it without closing the quick pick menu, if possible — commands that open windows outside of VS Code will still close the quick pick menu unless [`"gitlens.advanced.quickPick.closeOnFocusOut": false`](#extension-settings) is set

- Adds a `Show Repository Status` command (`gitlens.showQuickRepoStatus`) with a shortcut of `alt+s` to show a **repository status quick pick menu** for visualizing the current repository status

  ![Repository Status Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-repo-status.png)

  - Quickly see upstream status (if an Git upstream is configured) — complete with ahead and behind information
    - If you are ahead of the upstream, an entry will be shown with the number of commits ahead. Chosing it will show a limited **branch history quick pick menu** containing just the commits ahead of the upstream
    - If you are behind the upstream, an entry will be shown with the number of commits behind. Chosing it will show a limited **branch history quick pick menu** containing just the commits behind the upstream
  - Quickly see all working changes, both staged and unstaged, complete with status indicators for adds, changes, renames, and deletes
  - Provides entries to `Show Stashed Changes`, `Open Changed Files`, and `Close Unchanged Files`
  - Use the `alt+right arrow` shortcut on an entry to execute it without closing the quick pick menu, if possible — commands that open windows outside of VS Code will still close the quick pick menu unless [`"gitlens.advanced.quickPick.closeOnFocusOut": false`](#extension-settings) is set
  - Use the `alt+right arrow` shortcut on a file entry in the `Staged Files` or `Unstaged Files` sections to preview the working file while leaving the quick pick menu open
    - NOTE: Once [vscode issue #10568](https://github.com/Microsoft/vscode/issues/10568) is resolved this will change to preview the comparison of the working file with the previous revision

- Adds a `Show Stashed Changes` command (`gitlens.showQuickStashList`) to show a **stashed changes quick pick menu** for exploring your repository stash history

  ![Stashed Changes Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-stash-list.png)

  - Provides entries to `Stash Changes`
  - Navigate back to the previous quick pick menu via `alt+left arrow`, if available

  - Chosing a stash entry shows a **stash details quick pick menu** which is very similar to the **commit details quick pick menu** above

    ![Stash Details Quick Pick Menu](https://raw.githubusercontent.com/eamodio/vscode-git-codelens/master/images/screenshot-stash-details.png)

    - Quickly see the set of files changed in the stash, complete with status indicators for adds, changes, renames, and deletes
    - Provides entries to `Copy Message to Clipboard`, `Directory Compare`, and `Open Changed Files`
    - Provides entries to `Apply Stashed Changes` and `Delete Stashed Changes` — both require a confirmation
    - Navigate back to the previous quick pick menu via `alt+left arrow`, if available
    - Use the `alt+right arrow` shortcut on an entry to execute it without closing the quick pick menu, if possible — commands that open windows outside of VS Code will still close the quick pick menu unless [`"gitlens.advanced.quickPick.closeOnFocusOut": false`](#extension-settings) is set
    - Use the `alt+right arrow` shortcut on a file entry in the `Changed Files` section to preview the current revision of the while leaving the quick pick menu open
      - NOTE: Once [vscode issue #10568](https://github.com/Microsoft/vscode/issues/10568) is resolved this will change to preview the comparison of the current revision with the previous one

- Adds a `Show Last Opened Quick Pick` command (`gitlens.showLastQuickPick`) with a shortcut of `alt+-` to quickly get back to where you were when the last GitLens quick pick menu closed

- Adds a `Open File History Explorer` command (`gitlens.showFileHistory`) to show a **file history explorer** (peek style) to visualize the history of a file
  - Likely to be deprecated in a future release, add your voice to [#66](https://github.com/eamodio/vscode-gitlens/issues/66) if you feel it should not be removed

- Adds a `Open Blame History Explorer` command (`gitlens.showBlameHistory`) to show a **blame history explorer** (peek style) to visualize the blame history of a file or code block
  - Likely to be deprecated in a future release, add your voice to [#66](https://github.com/eamodio/vscode-gitlens/issues/66) if you feel it should not be removed

#### And More

- Adds a `Copy Commit ID to Clipboard` command (`gitlens.copyShaToClipboard`) to copy the commit id (sha) of the active line to the clipboard

- Adds a `Copy Commit Message to Clipboard` command (`gitlens.copyMessageToClipboard`) to copy the commit message of the active line to the clipboard

- Adds a `Open Changed Files` command (`gitlens.openChangedFiles`) to open any files with working tree changes

- Adds a `Close Unchanged Files` command (`gitlens.closeUnchangedFiles`) to close any files without working tree changes

- Adds a `Apply Stashed Changes` command (`gitlens.stashApply`) to chose a stash entry to apply to the working tree from a quick pick menu

- Adds a `Stash Changes` command (`gitlens.stashSave`) to save any working tree changes to the stash — can optionally provide a stash message

## Insiders

Add [`"gitlens.insiders": true`](#general-extension-settings) to your settings to join the insiders channel and get early access to upcoming features. Be aware that because this provides early access expect there to be issues.

## Extension Settings

GitLens is highly customizable and provides many configuration settings to allow the personalization of almost all features

### General Settings

|Name | Description
|-----|------------
|`gitlens.insiders`|Opts into the insiders channel -- provides access to upcoming features
|`gitlens.outputLevel`|Specifies how much (if any) output will be sent to the GitLens output channel

### Blame Annotation Settings

#### File Blame Annotation Settings

|Name | Description
|-----|------------
|`gitlens.blame.file.annotationType`|Specifies the type of blame annotations that will be shown for the current file. `gutter` - adds an annotation to the beginning of each line. `hover` - shows annotations when hovering over each line
|`gitlens.blame.file.lineHighlight.enabled`|Specifies whether or not to highlight lines associated with the current line
|`gitlens.blame.file.lineHighlight.locations`|Specifies where the associated line highlights will be shown. `gutter` - adds a gutter glyph. `line` - adds a full-line highlight background color. `overviewRuler` - adds a decoration to the overviewRuler (scroll bar)
|`gitlens.annotations.file.gutter.format`|Specifies the format of the gutter blame annotations. Available tokens: `${id}` - commit id, `${author}` - commit author, `${message}` - commit message, `${ago}` - relative commit date (e.g. 1 day ago), `${date}` - formatted commit date (format specified by `gitlens.annotations.file.dateFormat`), `${authorAgo}` - commit author, relative commit date
|`gitlens.annotations.file.gutter.dateFormat`|Specifies how to format absolute dates (using the `${date}` token) in gutter blame annotations. See https://momentjs.com/docs/#/displaying/format/ for valid formats
|`gitlens.annotations.file.gutter.compact`|Specifies whether or not to compact (deduplicate) matching adjacent gutter blame annotations
|`gitlens.annotations.file.gutter.heatmap.enabled`|Specifies whether or not to provide a heatmap indicator in the gutter blame annotations
|`gitlens.annotations.file.gutter.heatmap.location`|Specifies where the heatmap indicators will be shown in the gutter blame annotations. `left` - adds a heatmap indicator on the left edge of the gutter blame annotations. `right` - adds a heatmap indicator on the right edge of the gutter blame annotations
|`gitlens.annotations.file.gutter.hover.details`|Specifies whether or not to provide a commit details hover annotation over the gutter blame annotations
|`gitlens.annotations.file.gutter.hover.wholeLine`|Specifies whether or not to trigger hover annotations over the whole line
|`gitlens.annotations.file.hover.heatmap.enabled`|Specifies whether or not to provide heatmap indicators on the left edge of each line
|`gitlens.annotations.file.hover.wholeLine`|Specifies whether or not to trigger hover annotations over the whole line

#### Line Blame Annotation Settings

|Name | Description
|-----|------------
|`gitlens.blame.line.enabled`|Specifies whether or not to provide a blame annotation for the current line
|`gitlens.blame.line.annotationType`|Specifies the type of blame annotations that will be shown for the current line. `trailing` - adds an annotation to the end of the current line. `hover` - shows annotations when hovering over the current line
|`gitlens.annotations.line.trailing.format`|Specifies the format of the trailing blame annotations. Available tokens: `${id}` - commit id, `${author}` - commit author, `${message}` - commit message, `${ago}` - relative commit date (e.g. 1 day ago), `${date}` - formatted commit date (format specified by `gitlens.annotations.currentLine.dateFormat`), `${authorAgo}` - commit author, relative commit date
|`gitlens.annotations.line.trailing.dateFormat`|Specifies how to format absolute dates (using the `${date}` token) in trailing blame annotations. See https://momentjs.com/docs/#/displaying/format/ for valid formats
|`gitlens.annotations.line.trailing.hover.details`|Specifies whether or not to provide a commit details hover annotation over the trailing blame annotations
|`gitlens.annotations.line.trailing.hover.changes`|Specifies whether or not to provide a changes (diff) hover annotation over the trailing blame annotations
|`gitlens.annotations.line.trailing.hover.wholeLine`|Specifies whether or not to trigger hover annotations over the whole line
|`gitlens.annotations.line.hover.details`|Specifies whether or not to provide a commit details hover annotation for the current line
|`gitlens.annotations.line.hover.changes`|Specifies whether or not to provide a changes (diff) hover annotation for the current line

### Code Lens Settings

|Name | Description
|-----|------------
|`gitlens.codeLens.enabled`|Specifies whether or not to provide any Git code lens
|`gitlens.codeLens.recentChange.enabled`|Specifies whether or not to show a `recent change` code lens showing the author and date of the most recent commit for the file or code block
|`gitlens.codeLens.recentChange.command`|Specifies the command to be executed when the `recent change` code lens is clicked. `gitlens.toggleFileBlame` - toggles file blame annotations. `gitlens.showBlameHistory` - opens the blame history explorer. `gitlens.showFileHistory` - opens the file history explorer. `gitlens.diffWithPrevious` - compares the current committed file with the previous commit. `gitlens.showQuickCommitDetails` - shows a commit details quick pick. `gitlens.showQuickCommitFileDetails` - shows a commit file details quick pick. `gitlens.showQuickFileHistory` - shows a file history quick pick. `gitlens.showQuickRepoHistory` - shows a branch history quick pick
|`gitlens.codeLens.authors.enabled`|Specifies whether or not to show an `authors` code lens showing number of authors of the file or code block and the most prominent author (if there is more than one)
|`gitlens.codeLens.authors.command`|Specifies the command to be executed when the `authors` code lens is clicked. `gitlens.toggleFileBlame` - toggles file blame annotations. `gitlens.showBlameHistory` - opens the blame history explorer. `gitlens.showFileHistory` - opens the file history explorer. `gitlens.diffWithPrevious` - compares the current committed file with the previous commit. `gitlens.showQuickCommitDetails` - shows a commit details quick pick. `gitlens.showQuickCommitFileDetails` - shows a commit file details quick pick. `gitlens.showQuickFileHistory` - shows a file history quick pick. `gitlens.showQuickRepoHistory` - shows a branch history quick pick
|`gitlens.codeLens.locations`|Specifies where Git code lens will be shown in the document. `document` - adds code lens at the top of the document. `containers` -  adds code lens at the start of container-like symbols (modules, classes, interfaces, etc). `blocks` -  adds code lens at the start of block-like symbols (functions, methods, properties, etc) lines. `custom` - adds code lens at the start of symbols contained in `gitlens.codeLens.locationCustomSymbols`
|`gitlens.codeLens.customLocationSymbols`|Specifies the set of document symbols where Git code lens will be shown in the document
|`gitlens.codeLens.perLanguageLocations`|Specifies where Git code lens will be shown in the document for the specified languages

### Status Bar Settings

|Name | Description
|-----|------------
|`gitlens.statusBar.enabled`|Specifies whether or not to provide blame information on the status bar
|`gitlens.statusBar.alignment`|Specifies the blame alignment in the status bar. `left` - align to the left,  `right` - align to the right
|`gitlens.statusBar.format`|Specifies the format of the blame information on the status bar. Available tokens: `${id}` - commit id, `${author}` - commit author, `${message}` - commit message, `${ago}` - relative commit date (e.g. 1 day ago), `${date}` - formatted commit date (format specified by `gitlens.statusBar.dateFormat`)
|`gitlens.statusBar.command`|Specifies the command to be executed when the blame status bar item is clicked. `gitlens.toggleFileBlame` - toggles file blame annotations. `gitlens.showBlameHistory` - opens the blame history explorer. `gitlens.showFileHistory` - opens the file history explorer. `gitlens.diffWithPrevious` - compares the current line commit with the previous. `gitlens.diffWithWorking` - compares the current line commit with the working tree. `gitlens.toggleCodeLens` - toggles Git code lens. `gitlens.showQuickCommitDetails` - shows a commit details quick pick. `gitlens.showQuickCommitFileDetails` - shows a commit file details quick pick. `gitlens.showQuickFileHistory` - shows a file history quick pick. `gitlens.showQuickRepoHistory` - shows a branch history quick pick
|`gitlens.statusBar.format`|Specifies the format of the status bar blame information. Available tokens: `${id}` - commit id, `${author}` - commit author, `${message}` - commit message, `${ago}` - relative commit date (e.g. 1 day ago), `${date}` - formatted commit date (format specified by `gitlens.statusBar.dateFormat`), `${authorAgo}` - commit author, relative commit date
|`gitlens.statusBar.dateFormat`|Specifies the date format of absolute dates shown in the blame information on the status bar. See https://momentjs.com/docs/#/displaying/format/ for valid formats

### Theme Settings

|Name | Description
|-----|------------
|`gitlens.theme.annotations.file.gutter.separateLines`|Specifies whether or not gutter blame annotations will be separated by a small gap
|`gitlens.theme.annotations.file.gutter.dark.backgroundColor`|Specifies the dark theme background color of the gutter blame annotations
|`gitlens.theme.annotations.file.gutter.light.backgroundColor`|Specifies the light theme background color of the gutter blame annotations
|`gitlens.theme.annotations.file.gutter.dark.foregroundColor`|Specifies the dark theme foreground color of the gutter blame annotations
|`gitlens.theme.annotations.file.gutter.light.foregroundColor`|Specifies the light theme foreground color of the gutter blame annotations
|`gitlens.theme.annotations.file.gutter.dark.uncommittedForegroundColor`|Specifies the dark theme foreground color of an uncommitted line in the gutter blame annotations
|`gitlens.theme.annotations.file.gutter.light.uncommittedForegroundColor`|Specifies the light theme foreground color of an uncommitted line in the gutter blame annotations
|`gitlens.theme.annotations.file.hover.separateLines`|Specifies whether or not hover blame annotations will be separated by a small gap (if heatmap is enabled)
|`gitlens.theme.annotations.line.trailing.dark.backgroundColor`|Specifies the dark theme background color of the trailing blame annotation
|`gitlens.theme.annotations.line.trailing.light.backgroundColor`|Specifies the light theme background color of the trailing blame annotation
|`gitlens.theme.annotations.line.trailing.dark.foregroundColor`|Specifies the dark theme foreground color of the trailing blame annotation
|`gitlens.theme.annotations.line.trailing.light.foregroundColor`|Specifies the light theme foreground color of the trailing blame annotation
|`gitlens.theme.lineHighlight.dark.backgroundColor`|Specifies the dark theme background color of the associated line highlights in blame annotations. Must be a valid css color
|`gitlens.theme.lineHighlight.light.backgroundColor`|Specifies the light theme background color of the associated line highlights in blame annotations. Must be a valid css color
|`gitlens.theme.lineHighlight.dark.overviewRulerColor`|Specifies the dark theme overview ruler color of the associated line highlights in blame annotations
|`gitlens.theme.lineHighlight.light.overviewRulerColor`|Specifies the light theme overview ruler color of the associated line highlights in blame annotations

### Advanced Settings

|Name | Description
|-----|------------
|`gitlens.advanced.toggleWhitespace.enabled`|Specifies whether or not to toggle whitespace off then showing blame annotations (*may* be required by certain fonts/themes)
|`gitlens.advanced.menus`|Specifies which commands will be added to which menus
|`gitlens.advanced.caching.enabled`|Specifies whether git output will be cached
|`gitlens.advanced.caching.maxLines`|Specifies the threshold for caching larger documents
|`gitlens.advanced.git`|Specifies the git path to use
|`gitlens.advanced.gitignore.enabled`|Specifies whether or not to parse the root .gitignore file for better performance (i.e. avoids blaming excluded files)
|`gitlens.advanced.maxQuickHistory`|Specifies the maximum number of QuickPick history entries to show
|`gitlens.advanced.quickPick.closeOnFocusOut`|Specifies whether or not to close the QuickPick menu when focus is lost

## Known Issues

- If the `Copy to * clipboard` commands don't work on Linux -- `xclip` needs to be installed. You can install it via `sudo apt-get install xclip`
- Visible whitespace causes issues ([vscode issue #11485](https://github.com/Microsoft/vscode/issues/11485)) with the `expanded` and `compact` blame annotation styles when using a non-monospace font -- set `"gitlens.advanced.toggleWhitespace.enabled": true` if you are using a non-monospace font

## Contributors

A big thanks to the people that have contributed to this project:

- Aurelio Ogliari ([@nobitagit](https://github.com/nobitagit)) — [contributions](https://github.com/eamodio/vscode-gitlens/commits?author=nobitagit)
- Zack Schuster ([@zackschuster](https://github.com/zackschuster)) — [contributions](https://github.com/eamodio/vscode-gitlens/commits?author=zackschuster)
