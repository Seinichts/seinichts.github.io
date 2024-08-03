+++
title = "My Doom Configuration"
author = ["Zelong Kuang"]
draft = false
+++

## Doom modules {#doom-modules}



### Modules {#modules}

Doom has this lovely _modular configuration base_ that takes a lot of work out of
configuring Emacs. Each module (when enabled) can provide a list of packages to
install (on `doom sync`) and configuration to be applied. The modules can also
have flags applied to tweak their behaviour.

<a id="code-snippet--init.el"></a>
```emacs-lisp { collapsed="t" }
;;; init.el -*- lexical-binding: t; -*-

;; This file controls what Doom modules are enabled and what order they load in.
;; Press 'K' on a module to view its documentation, and 'gd' to browse its directory.

(doom! :input
<<doom-input>>

:completion
<<doom-completion>>

:ui
<<doom-ui>>

:editor
<<doom-editor>>

:emacs
<<doom-emacs>>

:term
<<doom-term>>

:checkers
<<doom-checkers>>

:tools
<<doom-tools>>

:os
<<doom-os>>

:lang
<<doom-lang>>

:email
<<doom-email>>

:app
<<doom-app>>

:config
<<doom-config>>
)
```


#### Structure {#structure}

As you may have noticed by this point, this is a [literate](https://en.wikipedia.org/wiki/Literate_programming) configuration. Doom
has good support for this which we access though the `literate` module.

While we're in the <span class="inline-src language-elisp" data-lang="elisp">`:config`</span> section, we'll use Dooms nicer defaults,
along with the bindings and smartparens behaviour (the flags aren't documented,
but they exist).

<a id="code-snippet--doom-config"></a>
```emacs-lisp
literate
(default +bindings +smartparens)
```


#### Interface {#interface}

There's a lot that can be done to enhance Emacs' capabilities.
I reckon enabling half the modules Doom provides should do it.

<a id="code-snippet--doom-completion"></a>
```emacs-lisp
;; (company                   ; the ultimate code completion backend
;;  +childframe)
(corfu +icons +orderless +dabbrev)  ; complete with cap(f), cape and a flying feather!
;;helm                       ; the *other* search engine for love and life
;;ido                        ; the other *other* search engine...
;; (ivy                      ; a search engine for love and life
;;  +icons                   ; ... icons are nice
;;  +prescient)              ; ... I know what I want(ed)
(vertico +icons)             ; the search engine of the future
```

<a id="code-snippet--doom-ui"></a>
```emacs-lisp
;;deft                       ; notational velocity for Emacs
doom                         ; what makes DOOM look the way it does
doom-dashboard               ; a nifty splash screen for Emacs
doom-quit                    ; DOOM quit-message prompts when you quit Emacs
;; (emoji +unicode)          ; 🙂
;;fill-column                ; a `fill-column' indicator
hl-todo                      ; highlight TODO/FIXME/NOTE/DEPRECATED/HACK/REVIEW
;;hydra                      ; quick documentation for related commands
;; indent-guides              ; highlighted indent columns, notoriously slow
ligatures           ; ligatures and symbols to make your code pretty again
;;minimap                    ; show a map of the code on the side
modeline                     ; snazzy, Atom-inspired modeline, plus API
nav-flash                    ; blink the current line after jumping
;;neotree                    ; a project drawer, like NERDTree for vim
ophints                      ; highlight the region an operation acts on
(popup                       ; tame sudden yet inevitable temporary windows
 +all                        ; catch all popups that start with an asterix
 +defaults)                  ; default popup rules
;; (tabs                      ; an tab bar for Emacs
;;  +centaur-tabs)           ; ... with prettier tabs
treemacs                     ; a project drawer, like neotree but cooler
;; unicode                    ; extended unicode support for various languages
(vc-gutter +pretty)          ; vcs diff in the fringe
vi-tilde-fringe              ; fringe tildes to mark beyond EOB
(window-select +numbers)     ; visually switch windows
workspaces                   ; tab emulation, persistence & separate workspaces
zen                          ; distraction-free coding or writing
```

<a id="code-snippet--doom-editor"></a>
```emacs-lisp
(evil +everywhere)           ; come to the dark side, we have cookies
file-templates               ; auto-snippets for empty files
fold                         ; (nigh) universal code folding
(format +onsave)                     ; automated prettiness
;;god                        ; run Emacs commands without modifier keys
;;lispy                      ; vim for lisp, for people who don't like vim
multiple-cursors             ; editing in many places at once
;;objed                      ; text object editing for the innocent
;;parinfer                   ; turn lisp into python, sort of
rotate-text                  ; cycle region at point between text candidates
snippets                     ; my elves. They type so I don't have to
;;word-wrap                  ; soft wrapping with language-aware indent
```

<a id="code-snippet--doom-emacs"></a>
```emacs-lisp
(dired +icons)               ; making dired pretty [functional]
electric                     ; smarter, keyword-based electric-indent
(ibuffer +icons)             ; interactive buffer management
undo                         ; persistent, smarter undo for your inevitable mistakes
vc                           ; version-control and Emacs, sitting in a tree
```

<a id="code-snippet--doom-term"></a>
```emacs-lisp
;;eshell                     ; the elisp shell that works everywhere
;;shell                      ; simple shell REPL for Emacs
;;term                       ; basic terminal emulator for Emacs
vterm                        ; the best terminal emulation in Emacs
```

<a id="code-snippet--doom-checkers"></a>
```emacs-lisp
syntax                       ; tasing you for every semicolon you forget
;; spell                     ; tasing you for misspelling mispelling
grammar                      ; tasing grammar mistake every you make
```

<a id="code-snippet--doom-tools"></a>
```emacs-lisp
ansible                      ; a crucible for infrastructure as code
biblio                       ; Writes a PhD for you (citation needed)
;;debugger                   ; FIXME stepping through code, to help you add bugs
;;direnv                     ; be direct about your environment
;; docker                       ; port everything to containers
;;editorconfig               ; let someone else argue about tabs vs spaces
ein                        ; tame Jupyter notebooks with emacs
(eval)              ; run code, run (also, repls)
;;gist                       ; interacting with github gists
(lookup                      ; helps you navigate your code and documentation
 +dictionary                 ; dictionary/thesaurus is nice
 +docsets)                   ; ...or in Dash docsets locally
(lsp                          ; Language Server Protocol
 +peek)
(magit                       ; a git porcelain for Emacs
 +forge)                     ; interface with git forges
make                         ; run make tasks from Emacs
;;pass                       ; password manager for nerds
pdf                          ; pdf enhancements
;;prodigy                    ; FIXME[[id:983f436e-02a1-4d2f-b274-761523d5ff5a][Contratiction?.org]] managing external services & code builders
;; rgb                          ; creating color strings
;;taskrunner                 ; taskrunner for all your projects
;;terraform                  ; infrastructure as code
;;tmux                       ; an API for interacting with tmux
tree-sitter                ; syntax and parsing, sitting in a tree...
upload                       ; map local to remote projects via ssh/ftp
```

<a id="code-snippet--doom-os"></a>
```emacs-lisp
macos                      ; MacOS-specific commands
tty                          ; improve the terminal Emacs experience
```


#### Language support {#language-support}

We can be rather liberal with enabling support for languages as the associated
packages/configuration are (usually) only loaded when first opening an
associated file.

<a id="code-snippet--doom-lang"></a>
```emacs-lisp
;;agda                       ; types of types of types of types...
;;beancount                  ; mind the GAAP
(cc +lsp +tree-sitter)                  ; C > C++ == 1
;;clojure                    ; java with a lisp
;;common-lisp                ; if you've seen one lisp, you've seen them all
;;coq                        ; proofs-as-programs
;;crystal                    ; ruby at the speed of c
;;csharp                     ; unity, .NET, and mono shenanigans
data                         ; config/data formats
;;(dart +flutter)            ; paint ui and not much else
;;dhall                      ; JSON with FP sprinkles
;;elixir                     ; erlang done right
;;elm                        ; care for a cup of TEA?
emacs-lisp                   ; drown in parentheses
;;erlang                     ; an elegant language for a more civilized age
ess                          ; emacs speaks statistics
;;faust                      ; dsp, but you get to keep your soul
;;fsharp                     ; ML stands for Microsoft's Language
;;fstar                      ; (dependent) types and (monadic) effects and Z3
;;gdscript                   ; the language you waited for
;;(graphql +lsp)             ; Give queries a REST
;; (go +lsp)                    ; the hipster dialect
(haskell +lsp)             ; a language that's lazier than I am
;;hy                         ; readability of scheme w/ speed of python
;;idris                      ;
json                         ; At least it ain't XML
;;(java +lsp)                ; the poster child for carpal tunnel syndrome
(javascript +lsp)            ; all(hope(abandon(ye(who(enter(here))))))
;; (julia +lsp)                 ; Python, R, and MATLAB in a blender
;;kotlin                     ; a better, slicker Java(Script)
(latex                       ; writing papers in Emacs has never been so fun
 +latexmk                    ; what else would you use?
 +lsp
 +cdlatex                    ; quick maths symbols
 +fold)                      ; fold the clutter away nicities
lean                       ; proof that mathematicians need help
;;factor                     ; for when scripts are stacked against you
;;ledger                     ; an accounting system in Emacs
lua                          ; one-based indices? one-based indices
markdown                     ; writing docs for people to ignore
;;nim                        ; python + lisp at the speed of c
;; nix                          ; I hereby declare "nix geht mehr!"
;;ocaml                      ; an objective camel
(org                         ; organize your plain life in plain text
 +dragndrop                  ; drag & drop files/images into org buffers
 +hugo                     ; use Emacs for hugo blogging
 +noter                      ; enhanced PDF notetaking
 +jupyter                    ; ipython/jupyter support for babel
 +pandoc                     ; export-with-pandoc support
 +gnuplot                    ; who doesn't like pretty pictures
 ;; +pomodoro                   ; be fruitful with the tomato technique
 +journal                    ; Record your life
 +present                    ; using org-mode for presentations
 +roam2)                     ; wander around notes
;;php                        ; perl's insecure younger brother
;;plantuml                   ; diagrams for confusing people more
;;purescript                 ; javascript, but functional
(python +lsp +pyright)       ; beautiful is better than ugly
;;qt                         ; the 'cutest' gui framework ever
;;racket                     ; a DSL for DSLs
;;raku                       ; the artist formerly known as perl6
;;rest                       ; Emacs as a REST client
;;rst                        ; ReST in peace
;;(ruby +rails)              ; 1.step {|i| p "Ruby is #{i.even? ? 'love' : 'life'}"}
(rust +lsp)                  ; Fe2O3.unwrap().unwrap().unwrap().unwrap()
;;scala                      ; java, but good
scheme                       ; a fully conniving family of lisps
sh                           ; she sells {ba,z,fi}sh shells on the C xor
;;sml                        ; no, the /other/ ML
;;solidity                   ; do you need a blockchain? No.
;;swift                      ; who asked for emoji variables?
;;terra                      ; Earth and Moon in alignment for performance.
;; web                          ; the tubes
yaml                         ; JSON, but readable
;; zig                          ; C, but simpler
```


#### Input {#input}

<a id="code-snippet--doom-input"></a>
```emacs-lisp
;;bidi                       ; (tfel ot) thgir etirw uoy gnipleh
;;chinese
;;japanese
;;layout                     ; auie,ctsrnm is the superior home row
```


#### Everything in Emacs {#everything-in-emacs}

It's just too convenient being able to have everything in Emacs.
I couldn't resist the Email and Feed modules.

<a id="code-snippet--doom-email"></a>
```emacs-lisp
;; (:if (executable-find "mu") (mu4e + org))
;;notmuch
;;(wanderlust +gmail)
```

<a id="code-snippet--doom-app"></a>
```emacs-lisp
;;calendar                   ; A dated approach to timetabling
;;emms                       ; Multimedia in Emacs is music to my ears
everywhere                   ; *leave* Emacs!? You must be joking.
irc                          ; how neckbeards socialize
;; (rss +org)                   ; emacs as an RSS reader
;;twitter                    ; twitter client https://twitter.com/vnought
```


### Disabled {#disabled}

```emacs-lisp
;; Disabled packages
(package! writegood-mode
  :disable t)
```


## Appearance {#appearance}


### Fonts {#fonts}

```emacs-lisp
(setq doom-font (font-spec :family "LXGW WenKai Mono" :size 22)
      doom-symbol-font (font-spec :family "JetbrainsMono Nerd Font" :size 22))
```


### Theme {#theme}

```emacs-lisp
(package! ef-themes)
```

```emacs-lisp
(setq doom-theme 'ef-tritanopia-light)
```


### Line numbers {#line-numbers}

This determines the style of line numbers in effect. If set to \`nil', line numbers are disabled. For relative line numbers, set this to \`relative'.

```emacs-lisp
(setq display-line-numbers-type `relative)
```


### Set default frame size {#set-default-frame-size}

```emacs-lisp
(add-to-list 'default-frame-alist '(height . 35))
(add-to-list 'default-frame-alist '(width . 80))
```


## Lang {#lang}


### Latex {#latex}

```emacs-lisp
(setq +latex-viewers '(pdf-tools))
(after! auctex
  (prettify-symbols-mode)
  (cdlatex-mode)
  (reftex-mode))
```


### Org {#org}


#### Org itself {#org-itself}

```emacs-lisp
(package! org :recipe
  (:host nil :repo "https://git.tecosaur.net/mirrors/org-mode.git" :remote "mirror" :fork
         (:host nil :repo "https://git.tecosaur.net/tec/org-mode.git" :branch "dev" :remote "tecosaur")
         :files
         (:defaults "etc")
         :build t :pre-build
         (with-temp-file "org-version.el"
           (require 'lisp-mnt)
           (let
               ((version
                 (with-temp-buffer
                   (insert-file-contents "lisp/org.el")
                   (lm-header "version")))
                (git-version
                 (string-trim
                  (with-temp-buffer
                    (call-process "git" nil t nil "rev-parse" "--short" "HEAD")
                    (buffer-string)))))
             (insert
              (format "(defun org-release () \"The release version of Org.\" %S)\n" version)
              (format "(defun org-git-version () \"The truncate git commit hash of Org mode.\" %S)\n" git-version)
              "(provide 'org-version)\n"))))
  :pin nil)

(unpin! org) ; there be bugs
```


#### Org directory {#org-directory}

If you use \`org' and don't want your org files in the default location below, change \`org-directory'. It must be set before org loads!

```emacs-lisp
(setq org-directory "~/OneDrive/org")
(setq org-roam-directory "~/OneDrive/org-note")
```


#### As a GTD tool {#as-a-gtd-tool}

<!--list-separator-->

-  Capture template

    Also, because I prefer "TODO" over "[ ]". So I overwrite the default template

    ```emacs-lisp
    (setq +org-capture-todo-file "inbox.org")
    (after! org
      (setq org-capture-templates
          '(("t" "Personal todo" entry
             (file+headline +org-capture-todo-file "Inbox")
             "* TODO %?\n%i\n%a" :prepend t)
            ("n" "Personal notes" entry
             (file+headline +org-capture-notes-file "Inbox")
             "* %u %?\n%i\n%a" :prepend t)
            ("j" "Journal" entry
             (file+olp+datetree +org-capture-journal-file)
             "* %U %?\n%i\n%a" :prepend t)
            ("p" "Templates for projects")
            ("pt" "Project-local todo" entry
             (file+headline +org-capture-project-todo-file "Inbox")
             "* TODO %?\n%i\n%a" :prepend t)
            ("pn" "Project-local notes" entry
             (file+headline +org-capture-project-notes-file "Inbox")
             "* %U %?\n%i\n%a" :prepend t)
            ("pc" "Project-local changelog" entry
             (file+headline +org-capture-project-changelog-file "Unreleased")
             "* %U %?\n%i\n%a" :prepend t)
            ("o" "Centralized templates for projects")
            ("ot" "Project todo" entry #'+org-capture-central-project-todo-file "* TODO %?\n %i\n %a" :heading "Tasks" :prepend nil)
            ("on" "Project notes" entry #'+org-capture-central-project-notes-file "* %U %?\n %i\n %a" :heading "Notes" :prepend t)
            ("oc" "Project changelog" entry #'+org-capture-central-project-changelog-file "* %U %?\n %i\n %a" :heading "Changelog" :prepend t))
          )
      )
    ```

<!--list-separator-->

-  Add a closed time when done

    ```emacs-lisp
    (setq org-log-done 'time)
    ```


#### Visuals {#visuals}

<!--list-separator-->

-  Org Modern

    Fontifying `org-mode` buffers to be as pretty as possible is of paramount importance,
    and Minad's lovely `org-modern` goes a long way in this regard.

    ```emacs-lisp
    (package! org-modern :pin "98532cd61795f3f41fffe7d4f0fa4021d8c73ffa")
    ```

    ...with a touch of configuration...

    ```emacs-lisp
    (use-package! org-modern
    :hook (org-mode . org-modern-mode)
    :config
    (setq org-modern-star '("⚀" "⚁" "⚂" "⚃" "⚄" "⚅")
    org-modern-table-vertical 1
    org-modern-table-horizontal 0.2
    org-modern-list '((43 . "➤")
            (45 . "–")
            (42 . "•"))
    org-modern-todo-faces
    '(("TODO" :inverse-video t :inherit org-todo)
    ("PROJ" :inverse-video t :inherit +org-todo-project)
    ("STRT" :inverse-video t :inherit +org-todo-active)
    ("[-]"  :inverse-video t :inherit +org-todo-active)
    ("HOLD" :inverse-video t :inherit +org-todo-onhold)
    ("WAIT" :inverse-video t :inherit +org-todo-onhold)
    ("[?]"  :inverse-video t :inherit +org-todo-onhold)
    ("KILL" :inverse-video t :inherit +org-todo-cancel)
    ("NO"   :inverse-video t :inherit +org-todo-cancel))
    org-modern-footnote
    (cons nil (cadr org-script-display))
    org-modern-block-fringe nil
    org-modern-block-name
    '((t . t)
    ("src" "»" "«")
    ("example" "»–" "–«")
    ("comment" "" "󰆄")
    ("quote" "❝" "❞")
    ("export" "" " "))
    ;; org-modern-progress nil
    ;; org-modern-priority nil
    org-modern-horizontal-rule (make-string 36 ?─)
    org-modern-checkbox
    '((88 . "") (45 . #("–" 0 2 (composition ((2))))) (32 . ""))
    org-modern-keyword
    '((t . t)
    ("title" . "󰗴")
    ("subtitle" . "󰨖")
    ("author" . "")
    ("email" . "")
    ("date" . "")
    ("property" . "󰠳")
    ("options" . #("󰘵" 0 1 (display (height 0.75))))
    ("startup" . "⏻")
    ("macro" . "󱡄")
    ("bind" . "󰌷")
    ("bibliography" . "")
    ("print_bibliography" . "󰌱")
    ("cite_export" . "↗")
    ("print_glossary" . "󰌱ᴬᶻ")
    ("glossary_sources" . "󰒻")
    ("include" . "⇤")
    ("setupfile" . "⇚")
    ("html_head" . "🅷")
    ("html" . "🅗")
    ("latex_class" . "🄻")
    ("latex_class_options" . "🄻󰒓")
    ("latex_header" . "🅻")
    ("latex_header_extra" . "🅻⁺")
    ("latex" . "🅛")
    ("beamer_theme" . "🄱")
    ("beamer_color_theme" . "🄱󰏘")
    ("beamer_font_theme" . "🄱")
    ("beamer_header" . "🅱")
    ("beamer" . "🅑")
    ("attr_latex" . "🄛")
    ("attr_html" . "🄗")
    ("attr_org" . "⒪")
    ("call" . "󰜎")
    ("name" . "⁍")
    ("header" . "›")
    ("caption" . "☰")
    ("results" . "")
    ("filetags" . "")
    ))
    (custom-set-faces! '(org-modern-statistics :inherit org-checkbox-statistics-todo)))
    ```

    Since `org-modern`'s tag face supplants Org's tag face, we need to adjust the
    spell-check face ignore list

    ```emacs-lisp
    (after! spell-fu
    (cl-pushnew 'org-modern-tag (alist-get 'org-mode +spell-excluded-faces-alist)))
    ```

<!--list-separator-->

-  Emphasis markers

    While `org-hide-emphasis-markers` is very nice, it can sometimes make edits which
    occur at the border a bit more fiddley. We can improve this situation without
    sacrificing visual amenities with the `org-appear` package.

    ```emacs-lisp
    (package! org-appear :recipe (:host github :repo "awth13/org-appear")
    :pin "81eba5d7a5b74cdb1bad091d85667e836f16b997")
    ```

    ```emacs-lisp
    (setq org-hide-emphasis-markers t)
    (use-package! org-appear
    :hook (org-mode . org-appear-mode)
    :config
    (setq org-appear-autoemphasis t
    org-appear-autosubmarkers t
    org-appear-autolinks nil)
    ;; for proper first-time setup, `org-appear--set-elements'
    ;; needs to be run after other hooks have acted.
    (run-at-time nil nil #'org-appear--set-elements))
    ```

<!--list-separator-->

-  Title size

    ```elisp
    (custom-set-faces
      '(org-level-1 ((t (:inherit outline-1 :height 1.15))))
      '(org-level-2 ((t (:inherit outline-2 :height 1.125))))
      '(org-level-3 ((t (:inherit outline-3 :height 1.1))))
      '(org-level-4 ((t (:inherit outline-4 :height 1.075))))
      '(org-level-5 ((t (:inherit outline-5 :height 1.05))))
      '(org-level-6 ((t (:inherit outline-6 :height 1.025))))
      '(org-document-title ((t (:height 1.8 :underline t))))
    )
    ```

<!--list-separator-->

-  Reduced indent

    Thanks to the various bits and bobs of setup we have here, the non-heading lines tend to appear over-indented in org-indent-mode. We can adjust this by modifying the generated text prefixes.

    There’s another issue we can have when using mixed-pitch mode, where the line height is set by the indent prefix displayed with the fixed-pitch font. This means that on 0-indent lines the line spacing can be different, which doesn’t look very good. We can also solve this problem by modifying the generated text prefixes to but a fixed-pitch zero width space at the start of 0-indent lines instead of nothing.

    ```emacs-lisp
    (defadvice! +org-indent--reduced-text-prefixes ()
      :after #'org-indent--compute-prefixes
      (setq org-indent--text-line-prefixes
            (make-vector org-indent--deepest-level nil))
      (when (> org-indent-indentation-per-level 0)
        (dotimes (n org-indent--deepest-level)
          (aset org-indent--text-line-prefixes
                n
                (org-add-props
                    (concat (make-string (* n (1- org-indent-indentation-per-level))
                                         ?\s)
                            (if (> n 0)
                                 (char-to-string org-indent-boundary-char)
                              "\u200b"))
                    nil 'face 'org-indent)))))
    ```

<!--list-separator-->

-  Center images

    ```emacs-lisp
    (setq org-image-align 'center)
    ```

<!--list-separator-->

-  Prettify

    ```emacs-lisp
    (add-hook! 'org-mode-hook #'+org-pretty-mode)
    ```

<!--list-separator-->

-  Sticky header

    ```emacs-lisp
    (package! org-sticky-header)
    ```

    ```emacs-lisp
    (use-package! org-sticky-header
      :hook (org-mode . org-sticky-header-mode))
    ```


#### Latex in org {#latex-in-org}

<!--list-separator-->

-  Syntax highlighting

    ```emacs-lisp
    (setq org-highlight-latex-and-related '(native latex entities))
    (after! org (org-toggle-pretty-entities))

    ```

<!--list-separator-->

-  Org latex preview

    ```emacs-lisp
    (use-package org-latex-preview
      :config
      ;; Increase preview width
      (plist-put org-latex-preview-appearance-options
                 :page-width 0.8)

      ;; Use dvisvgm to generate previews
      ;; You don't need this, it's the default:
      (setq org-latex-preview-process-default 'dvisvgm)

      ;; Turn on auto-mode, it's built into Org and much faster/more featured than
      ;; org-fragtog. (Remember to turn off/uninstall org-fragtog.)
      (add-hook 'org-mode-hook 'org-latex-preview-auto-mode)

      ;; Block C-n and C-p from opening up previews when using auto-mode
      (add-hook 'org-latex-preview-auto-ignored-commands 'next-line)
      (add-hook 'org-latex-preview-auto-ignored-commands 'previous-line)

      ;; Enable consistent equation numbering
      (setq org-latex-preview-numbered t)

      ;; Bonus: Turn on live previews.  This shows you a live preview of a LaTeX
      ;; fragment and updates the preview in real-time as you edit it.
      ;; To preview only environments, set it to '(block edit-special) instead
      (setq org-latex-preview-live '(inline block edit-special))

      ;; More immediate live-previews -- the default delay is 1 second
      (setq org-latex-preview-live-debounce 0.4))

    (defun latex-preview ()
      (interactive)
      (execute-kbd-macro (kbd "SPC u SPC u C-c C-x C-l")))

    (map! :leader
          :desc "Latex preview"
          :n "l l" #'latex-preview)
    ```

    <!--list-separator-->

    -  Dvisvgm setting

        ```emacs-lisp
        (thread-first (alist-get 'dvisvgm org-latex-preview-process-alist)
                      (plist-get :image-converter)
                      (setf "dvisvgm --page=1- --libgs=/opt/homebrew/bin/gs --optimize --clipjoin --relative --no-fonts --bbox=preview -o %B-%%9p.svg %f")
                      )
        ```

    <!--list-separator-->

    -  Always center displaymath

        ```emacs-lisp
        (use-package! org-latex-preview
          :config
          (defun my/org-latex-preview-uncenter (ov)
            (overlay-put ov 'before-string nil))
          (defun my/org-latex-preview-recenter (ov)
            (overlay-put ov 'before-string (overlay-get ov 'justify)))
          (defun my/org-latex-preview-center (ov)
            (save-excursion
              (goto-char (overlay-start ov))
              (when-let* ((elem (org-element-context))
                          ((or (eq (org-element-type elem) 'latex-environment)
                               (string-match-p "^\\\\\\[" (org-element-property :value elem))))
                          (img (overlay-get ov 'display))
                          (prop `(space :align-to (- center (0.55 . ,img))))
                          (justify (propertize " " 'display prop 'face 'default)))
                (overlay-put ov 'justify justify)
                (overlay-put ov 'before-string (overlay-get ov 'justify)))))
          (define-minor-mode org-latex-preview-center-mode
            "Center equations previewed with `org-latex-preview'."
            :global nil
            (if org-latex-preview-center-mode
                (progn
                  (add-hook 'org-latex-preview-overlay-open-functions
                            #'my/org-latex-preview-uncenter nil :local)
                  (add-hook 'org-latex-preview-overlay-close-functions
                            #'my/org-latex-preview-recenter nil :local)
                  (add-hook 'org-latex-preview-overlay-update-functions
                            #'my/org-latex-preview-center nil :local))
              (remove-hook 'org-latex-preview-overlay-close-functions
                            #'my/org-latex-preview-recenter)
              (remove-hook 'org-latex-preview-overlay-update-functions
                            #'my/org-latex-preview-center)
              (remove-hook 'org-latex-preview-overlay-open-functions
                            #'my/org-latex-preview-uncenter))))
        ```

        And add hook onto org mode

        ```emacs-lisp
        (add-hook! 'org-mode-hook #'org-latex-preview-center-mode)
        ```

    <!--list-separator-->

    -  Health check

        ```emacs-lisp
        (defun org-latex-preview-check-health (&optional inter)
          "Inspect the relevent system state and setup.
        INTER signals whether the function has been called interactively."
          (interactive (list t))
          ;; Collect information
          (let* ((diag `(:interactive ,inter)))
            (plist-put diag :org-version org-version)
            ;; modified variables
            (plist-put diag :modified
                       (let ((list))
                         (mapatoms
                          (lambda (v)
                            (and (boundp v)
                                 (string-match "\\`\\(org-latex-\\|org-persist-\\)" (symbol-name v))
                                 (or (and (symbol-value v)
                                          (string-match "\\(-hook\\|-function\\)\\'" (symbol-name v)))
                                     (and
                                      (get v 'custom-type) (get v 'standard-value)
                                      (not (equal (symbol-value v)
                                                  (eval (car (get v 'standard-value)) t)))))
                                 (push (cons v (symbol-value v)) list))))
                         list))
            ;; Executables
            ;; latex processors
            (dolist (processor org-latex-compilers)
              (when-let ((path (executable-find processor)))
                (let ((version (with-temp-buffer
                                 (thread-last
                                   (concat processor " --version")
                                   (shell-command-to-string)
                                   (insert))
                                 (goto-char (point-min))
                                 (buffer-substring (point) (line-end-position)))))
                  (push (list processor version path) (plist-get diag :latex-processors)))))
            ;; Image converters
            (dolist (converter '("dvipng" "dvisvgm" "convert"))
              (when-let ((path (executable-find converter)))
                (let ((version (with-temp-buffer
                                 (thread-last
                                   (concat converter " --version")
                                   (shell-command-to-string)
                                   (insert))
                                 (goto-char (point-min))
                                 (buffer-substring (point) (line-end-position)))))
                  (push (list converter version path) (plist-get diag :image-converters)))))
            (when inter
              (with-current-buffer (get-buffer-create "*Org LaTeX Preview Report*")
                (let ((inhibit-read-only t))
                  (erase-buffer)

                  (insert (propertize "Your LaTeX preview process" 'face 'outline-1))
                  (insert "\n\n")

                  (let* ((latex-available (cl-member org-latex-compiler
                                                     (plist-get diag :latex-processors)
                                                     :key #'car :test #'string=))
                         (precompile-available
                          (and latex-available
                               (not (member org-latex-compiler '("lualatex" "xelatex")))))
                         (proc-info (alist-get
                                     org-latex-preview-process-default
                                     org-latex-preview-process-alist))
                         (image-converter (cadr (plist-get proc-info :programs)))
                         (image-converter
                          (cl-find-if
                           (lambda (c)
                             (string= image-converter c))
                           (plist-get diag :image-converters)
                           :key #'car))
                         (image-output-type (plist-get proc-info :image-output-type)))
                    (if org-latex-preview-process-precompiled
                        (insert "Precompile with "
                                (propertize (map-elt org-latex-precompile-compiler-map
                                                     org-latex-compiler)
                                            'face
                                            (list
                                             (if precompile-available
                                                 '(:inherit success :box t)
                                               '(:inherit error :box t))
                                             'org-block))
                                " → "))
                    (insert "LaTeX Compile with "
                            (propertize org-latex-compiler 'face
                                        (list
                                         (if latex-available
                                             '(:inherit success :box t)
                                           '(:inherit error :box t))
                                         'org-block))
                            " → ")
                    (insert "Convert to "
                            (propertize (upcase image-output-type) 'face '(:weight bold))
                            " with "
                            (propertize (car image-converter) 'face
                                        (list
                                         (if image-converter
                                             '(:inherit success :box t)
                                           '(:inherit error :box t))
                                         'org-block))
                            "\n\n")
                    (insert (propertize org-latex-compiler 'face 'outline-3)
                            "\n"
                            (if latex-available
                                (concat
                                  (propertize
                                   (mapconcat #'identity (map-nested-elt diag `(:latex-processors ,org-latex-compiler))
                                              "\n")
                                   'face 'org-block)
                                  "\n"
                                  (when (and latex-available (not precompile-available))
                                    (propertize
                                     (format "\nWarning: Precompilation not available with %S!\n" org-latex-compiler)
                                     'face 'warning)))
                              (propertize "Not found in path!\n" 'face 'error))
                            "\n")

                    (insert (propertize (cadr (plist-get proc-info :programs)) 'face 'outline-3)
                            "\n"
                            (if image-converter
                                (propertize
                                 (concat
                                  (mapconcat #'identity (cdr image-converter) "\n")
                                  "\n")
                                 'face 'org-block)
                              (propertize "Not found in path!\n" 'face 'error))
                            "\n")
                    ;; dvisvgm version check
                    (when (equal (car-safe image-converter)
                                 "dvisvgm")
                      (let* ((version-string (cadr image-converter))
                             (dvisvgm-ver (progn
                                            (string-match "\\([0-9.]+\\)" version-string)
                                            (match-string 1 version-string))))

                        (when (version< dvisvgm-ver "3.0")
                          (insert (propertize
                                   (format "Warning: dvisvgm version %s < 3.0, displaymath will not be centered."
                                           dvisvgm-ver)
                                   'face 'warning)
                                  "\n\n"))
                        (unless (string-match-p " RSVG" system-configuration-features)
                          (insert (propertize
                                   "Error: Emacs was not compiled with SVG support,
        images cannot be displayed with dvisvgm"
                                   'face 'error)))))
                    ;; png support check
                    (when (member (car-safe image-converter)
                                  '("dvipng" "convert"))
                      (unless (string-match-p " PNG" system-configuration-features)
                        (insert (propertize
                                 (format "Error: Emacs was not compiled with PNG support,
        images cannot be displayed with %s"
                                         (car-safe image-converter))))))
                    (when (not (and latex-available image-converter))
                      (insert "path: " (getenv "PATH") "\n\n")))
                  ;; Settings
                  (insert (propertize "LaTeX preview options" 'face 'outline-2)
                          "\n")

                  (pcase-dolist (`(,var . ,msg)
                                 `((,org-latex-preview-process-precompiled . "Precompilation           ")
                                   (,org-latex-preview-numbered . "Equation renumbering     ")
                                   (,org-latex-preview-cache  . "Caching with org-persist ")))
                    (insert (propertize "• " 'face 'org-list-dt)
                            msg
                            (if var
                                (propertize "ON" 'face '(success bold org-block))
                              (propertize "OFF" 'face '(error bold org-block)))
                            "\n"))
                  (insert "\n"
                          (propertize "LaTeX preview sizing" 'face 'outline-2) "\n"
                          (propertize "•" 'face 'org-list-dt)
                          " Page width  "
                          (propertize
                           (format "%S" (plist-get org-latex-preview-appearance-options :page-width))
                           'face '(org-code org-block))
                          "   (display equation width in LaTeX)\n"
                          (propertize "•" 'face 'org-list-dt)
                          " Scale       "
                          (propertize
                           (format "%.2f" (plist-get org-latex-preview-appearance-options :scale))
                           'face '(org-code org-block))
                          "  (PNG pixel density multiplier)\n"
                          (propertize "•" 'face 'org-list-dt)
                          " Zoom        "
                          (propertize
                           (format "%.2f" (plist-get org-latex-preview-appearance-options :zoom))
                           'face '(org-code org-block))
                          "  (display scaling factor)\n\n")
                  (insert (propertize "LaTeX preview preamble" 'face 'outline-2) "\n")
                  (let ((major-mode 'org-mode))
                    (let ((point-1 (point)))
                      (insert org-latex-preview-preamble "\n")
                      (org-src-font-lock-fontify-block 'latex point-1 (point))
                      (add-face-text-property point-1 (point) '(:inherit org-block :height 0.9)))
                    (insert "\n")
                    ;; Diagnostic output
                    (insert (propertize "Diagnostic info (copied)" 'face 'outline-2)
                            "\n\n")
                    (let ((point-1 (point)))
                      (pp diag (current-buffer))
                      (org-src-font-lock-fontify-block 'emacs-lisp point-1 (point))
                      (add-face-text-property point-1 (point) '(:height 0.9))))
                  (gui-select-text (prin1-to-string diag))
                  (special-mode))
                (setq-local
                 revert-buffer-function
                 (lambda (&rest _)
                   (call-interactively #'org-latex-preview-check-health)
                   (message "Refreshed LaTeX preview diagnostic")))
                (let ((message-log-max nil))
                  (toggle-truncate-lines 1))
                (goto-char (point-min))
                (display-buffer (current-buffer))))
            diag))
        ```

<!--list-separator-->

-  latex editing

    <!--list-separator-->

    -  Prettify symbols

        ```emacs-lisp
        (setq  org-pretty-entities nil
               org-pretty-entities-include-sub-superscripts nil
        )
        ```

    <!--list-separator-->

    -  cdlatex in org

        ```emacs-lisp
        (add-hook! 'org-mode-hook #'org-cdlatex-mode)
        ```

        <!--list-separator-->

        -  ' key modify

            ```emacs-lisp
            (setq cdlatex-math-modify-alist
                  '((?t "\\mathbb" "" t nil nil)
                    (?v "\\vec" "" t nil nil)
                    (?> "\\check" "" t nil nil)
                    (?s "\\sqrt" "" t nil nil)
                    (?a "| ? |" nil nil nil nil)
                    (?l "\\text" "" t t nil)
                    ))
            ```

        <!--list-separator-->

        -  symbol alist modify

            ```emacs-lisp
            (defun my/set-cdlatex-math-symbol-alist ()
                    (setq cdlatex-math-symbol-alist
                          '((?0 ("\\varnothing" "\\emptyset"))
                            (?1 ("\\ONE" "\\one"))
                            (?. ("\\cdot" "\\circ"))
                            (?v ("\\vee" "\\bigvee"))
                            (?& ("\\wedge" "\\bigwedge"))
                            (?9 ("\\cap" "\\bigcap" "\\bigoplus"))
                            (?+ ("\\cup" "\\bigcup" "\\oplus"))
                            (?- ("\\rightharpoonup" "\\hookrightarrow" "\\circlearrowleft"))
                            (?= ("\\equiv" "\\Leftrightarrow" "\\Longleftrightarrow"))
                            (?~ ("\\sim" "\\approx" "\\propto"))
                            (?L ("\\Lambda" "\\limits"))
                            (?* ("\\times" "\\otimes" "\\bigotimes"))
                            (?e ("\\eps" "\\epsilon" "\\exp\\Big( ? \\Big)"))
                            (?> ("\\mapsto" "\\longrightarrow" "\\rightrightarrows"))
                            (?< ("\\preceq" "\\leftarrow" "\\longleftarrow"))
                            (?| ("\\parallel" "\\mid" "\\perp"))
                            (?S ("\\Sigma" "\\sum_{?}^{}"))
                            (?{ ("\\subset" "\\prec" "\\subseteq"))
                            (?} ("\\supset" "\\succ" "\\supseteq")))))
            ```

    <!--list-separator-->

    -  reftex

        ```emacs-lisp
        (add-hook! 'org-mode-hook #'reftex-mode)
        ```

<!--list-separator-->

-  latex packages

    ```emacs-lisp
    (setq org-latex-packages-alist
          '(("" "amsmath" t)
            ("T1" "fontenc" t)
            ("" "bm" t) ; Bold math required
            ("" "mathtools" t)
            ("" "siunitx" t)
            ("" "physics2" t)
            ("" "amssymb" t)
    	("" "algpseudocode" t)
            ("" "mlmodern" t)))

    (setq org-latex-preview-preamble
          "\\documentclass{article}
    [DEFAULT-PACKAGES]
    [PACKAGES]
    \\usepackage{xcolor}
    \\usephysicsmodule{ab,ab.braket,diagmat,xmat}%
    ")
    ```


#### Org Roam {#org-roam}

```emacs-lisp
(package! org-roam-ui)
```

```emacs-lisp
(map! :after evil :leader :desc "toggle org roam ui" :n "n r u" #'org-roam-ui-mode)
(setq org-roam-node-display-template
      (concat "${title:*} "
              " "
              (propertize "${doom-tags:42}" 'face '(:inherit org-tag :box nil))))
```

<!--list-separator-->

-  Roam template

    Default template included too much auxiliary details, only need dates included

    ```emacs-lisp

    (setq org-roam-capture-templates
          '(("d" "default" plain "%?" :target
            (file+head "%<%Y%m%d>-${slug}.org" "#+title: ${title}\n")
            :unnarrowed t)))
    ```

    |   |         |       |    |         |                                                          |
    |---|---------|-------|----|---------|----------------------------------------------------------|
    | d | default | plain | %? | :target | (file+head %&lt;%Y%m%d&gt;-${slug}.org #+title: ${title} |

    ) |:unnarrowed |t |


#### LSP support in `src` blocks {#lsp-support-in-src-blocks}

Now, by default, LSPs don't really function at all in `src` blocks.

```emacs-lisp
(cl-defmacro lsp-org-babel-enable (lang)
"Support LANG in org source code block."
(setq centaur-lsp 'lsp-mode)
(cl-check-type lang string)
(let* ((edit-pre (intern (format "org-babel-edit-prep:%s" lang)))
    (intern-pre (intern (format "lsp--%s" (symbol-name edit-pre)))))
`(progn
(defun ,intern-pre (info)
    (let ((file-name (->> info caddr (alist-get :file))))
    (unless file-name
        (setq file-name (make-temp-file "babel-lsp-")))
    (setq buffer-file-name file-name)
    (lsp-deferred)))
(put ',intern-pre 'function-documentation
    (format "Enable lsp-mode in the buffer of org source block (%s)."
            (upcase ,lang)))
(if (fboundp ',edit-pre)
    (advice-add ',edit-pre :after ',intern-pre)
    (progn
    (defun ,edit-pre (info)
        (,intern-pre info))
    (put ',edit-pre 'function-documentation
        (format "Prepare local buffer environment for org source block (%s)."
                (upcase ,lang))))))))
(defvar org-babel-lang-list
'("go" "python" "ipython" "bash" "sh"))
(dolist (lang org-babel-lang-list)
(eval `(lsp-org-babel-enable ,lang)))
```


#### Export-to {#export-to}

<!--list-separator-->

-  Latex

    By default Org uses pdflatex × 3 + bibtex. This simply won’t do in our modern world. latexmk + biber (which is used automatically with latexmk) is a simply superior combination.

    ```emacs-lisp
    ;; org-latex-compilers = ("pdflatex" "xelatex" "lualatex"), which are the possible values for %latex
    (setq org-latex-pdf-process '("latexmk -pdf -shell-escape -interaction=nonstopmode -output-directory=%o %f"))
    ```

    While org-latex-pdf-process does support a function, and we could use that instead, this would no longer use the log buffer — it’s a bit blind, you give it the file name and expect it to do its thing.

    The default values of org-latex-compilers is given in commented form to see how org-latex-pdf-process works with them.

<!--list-separator-->

-  Hugo

    org-export-with-buffer-copy no longer exists in latest version

    ```emacs-lisp
    (defun org-html-format-latex (latex-frag processing-type info)
      "Format a LaTeX fragment LATEX-FRAG into HTML.
    PROCESSING-TYPE designates the tool used for conversion.  It can
    be `mathjax', `verbatim', `html', nil, t or symbols in
    `org-preview-latex-process-alist', e.g., `dvipng', `dvisvgm' or
    `imagemagick'.  See `org-html-with-latex' for more information.
    INFO is a plist containing export properties."
      (let ((cache-relpath "") (cache-dir ""))
        (unless (or (eq processing-type 'mathjax)
                    (eq processing-type 'html))
          (let ((bfn (or (buffer-file-name)
                 (make-temp-name
                  (expand-file-name "latex" temporary-file-directory))))
            (latex-header
             (let ((header (plist-get info :latex-header)))
               (and header
                (concat (mapconcat
                     (lambda (line) (concat "#+LATEX_HEADER: " line))
                     (org-split-string header "\n")
                     "\n")
                    "\n")))))
        (setq cache-relpath
              (concat (file-name-as-directory org-preview-latex-image-directory)
                  (file-name-sans-extension
                   (file-name-nondirectory bfn)))
              cache-dir (file-name-directory bfn))
        ;; Re-create LaTeX environment from original buffer in
        ;; temporary buffer so that dvipng/imagemagick can properly
        ;; turn the fragment into an image.
        (setq latex-frag (concat latex-header latex-frag))))
        (with-temp-buffer
          (insert latex-frag)
          (org-format-latex cache-relpath nil nil cache-dir nil
                "Creating LaTeX Image..." nil processing-type)
          (buffer-string))))

    (setq org-hugo-base-dir "~/orgblog/")
    ```


#### jupyter in org {#jupyter-in-org}

For somehow reason, emacs cannot detect my python and need this line to work.

```emacs-lisp
(after! (ob-jupyter)
  (org-babel-jupyter-aliases-from-kernelspecs))
```


#### org-noter {#org-noter}

<!--list-separator-->

-  nov and djvu package

    These packages are required for unknown reasons. Install to avoid repeating warning

    ```emacs-lisp
    (package! nov)
    (package! djvu)
    ```


#### org-download-dir {#org-download-dir}

```emacs-lisp
(setq-default org-download-image-dir )
```


### SageMath {#sagemath}

```emacs-lisp
(package! sage-shell-mode)
(package! ob-sagemath)
```

```emacs-lisp
(use-package! ob-sagemath ;; Ob-sagemath supports only evaluating with a session.
  :config
  (setq org-babel-default-header-args:sage '((:session . t)
                                             (:results . "output")))

  ;; C-c c for asynchronous evaluating (only for SageMath code blocks).
  (with-eval-after-load "org"
    (define-key org-mode-map (kbd "C-c c") 'ob-sagemath-execute-async))

  ;; Do not confirm before evaluation
  (setq org-confirm-babel-evaluate nil)

  ;; Do not evaluate code blocks when exporting.
  (setq org-export-babel-evaluate nil)

  ;; Show images when opening a file.
  (setq org-startup-with-inline-images t)

  ;; Set sage root
  (setq sage-shell:sage-root "~/miniforge3/envs/sage/bin")

  ;; Show images after evaluating code blocks.
  (add-hook 'org-babel-after-execute-hook 'org-display-inline-images))
```


## Edit {#edit}


### Yasnippet auto-expand {#yasnippet-auto-expand}

```emacs-lisp
;; Function that tries to autoexpand YaSnippets
;; The double quoting is NOT a typo!
(defun my/yas-try-expanding-auto-snippets ()
  (when (and (boundp 'yas-minor-mode) yas-minor-mode)
    (let ((yas-buffer-local-condition ''(require-snippet-condition . auto)))
      (yas-expand))))
;; Try after every insertion
(add-hook 'post-self-insert-hook #'my/yas-try-expanding-auto-snippets)

(add-to-list 'warning-suppress-types '(yasnippet backquote-change))
```


### File-templates dir {#file-templates-dir}

```emacs-lisp
(setq +file-templates-dir "~/.config/doom/file-templates/")
```


## Programming {#programming}


### vterm {#vterm}


#### default shell {#default-shell}

```emacs-lisp
(setq shell-file-name (executable-find "bash"))
(setq-default vterm-shell (executable-find "fish"))
```


### Quickrun {#quickrun}

```emacs-lisp
(map! :after evil :desc "quickrun" :n "<f1>" #'quickrun)
```


### Tabnine {#tabnine}

```emacs-lisp
(package! tabnine)
(package! tabnine-capf
  :recipe (:host github :repo "50ways2sayhard/tabnine-capf" :files ("*.el" "*.sh")))
```

```emacs-lisp
(use-package! tabnine
  :hook (((prog-mode vterm-mode). tabnine-mode)
	 (kill-emacs . tabnine-kill-process))
  :config
  (add-to-list 'completion-at-point-functions #'tabnine-completion-at-point)
  (tabnine-start-process)
  :bind
  (:map  tabnine-completion-map
	("<tab>" . tabnine-accept-completion)
	("TAB" . tabnine-accept-completion)
	("M-f" . tabnine-accept-completion-by-word)
	("M-<return>" . tabnine-accept-completion-by-line)
	("C-g" . tabnine-clear-overlay)
	("M-[" . tabnine-previous-completion)
	("M-]" . tabnine-next-completion))
  )

(when (fboundp #'tabnine-completion-at-point)
  (add-hook 'lsp-completion-mode-hook
            (defun lsp-capf ()
              (remove-hook 'completion-at-point-functions #'lsp-completion-at-point t)
              (add-hook 'completion-at-point-functions
                        (cape-capf-super
                         #'lsp-completion-at-point
                         #'tabnine-completion-at-point) nil t))))

(use-package tabnine-capf
  :after cape
  :hook (kill-emacs . tabnine-capf-kill-process)
  :config
  (add-to-list 'completion-at-point-functions #'tabnine-completion-at-point))
```


### Stick scroll {#stick-scroll}

```emacs-lisp
(add-to-list 'semantic-default-submodes 'global-semantic-stickyfunc-mode)
(add-hook! 'prog-mode-hook #'semantic-mode)
```
