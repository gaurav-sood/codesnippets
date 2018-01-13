;; Personal Details
(setq user-full-name "Gaurav Sood")
(setq user-mail-address "mail.sood@gmail.com")
;; Repo Init
(require 'package)
(add-to-list 'package-archives '("melpa-stable" . "http://stable.melpa.org/packages/"))
(package-initialize)
;;Global Settings
(setq backup-directory-alist '(("" . "~/.emacs.d/emacs-backup")))
(global-auto-revert-mode 1)
(column-number-mode)
(global-linum-mode)
(add-hook 'after-init-hook 'global-company-mode)
(global-auto-revert-mode)
;; Text Completion Framework
;; Incremental Completion
;; Narrowing Selection
(projectile-global-mode)
(setq projectile-completion-system 'helm)
(helm-projectile-on)
;; (setq projectile-enable-caching t)
;; Python
(require 'virtualenvwrapper)
(venv-initialize-eshell)
(venv-initialize-interactive-shells)
(setq venv-location "/home/gaurav/.virtualenv/")
(setq-default mode-line-format (cons '(:exec venv-current-name) mode-line-format))

(require 'company-jedi)
(defun my/python-mode-hook ()
  (add-to-list 'company-backends 'company-jedi))
(add-hook 'python-mode-hook 'my/python-mode-hook)
(add-hook 'python-mode-hook 'py-autopep8-enable-on-save)
(setq jedi:environment-root "py3")
(setq jedi:environment-virtualenv (list "virtualenv" "--system-site-packages"
					"--python" "/home/gaurav/.virtualenv/py3.6.3/bin/python3"))
(setq jedi:server-args (list "--virtual-env" "/home/gaurav/.virtualenv/py3.6.3"))
(jedi:install-server)
(venv-workon "py3.6.3")
(add-hook 'python-mode-hook
	  '(lambda ()
	     (local-set-key (kbd "C-c .") 'jedi:goto-definition)
	     (local-set-key (kbd "C-c ,") 'jedi:goto-definition-pop-marker)
	     (local-set-key (kbd "C-c d") 'jedi:show-doc)
	     (local-set-key (kbd "C-<tab>") 'jedi:complete)))
(add-hook 'python-mode-hook 'jedi:setup)
;; Haskell
(add-hook 'haskell-mode-hook 'intero-mode)
(custom-set-variables
 ;; custom-set-variables was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 '(package-selected-packages
   (quote
    (use-package intero virtualenvwrapper py-autopep8 company-jedi helm-projectile company))))
(custom-set-faces
 ;; custom-set-faces was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 )
