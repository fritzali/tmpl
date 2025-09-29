## Templates

This repository includes `LaTeX` templates for different document types. The following briefly describes how to obtain a current `TeXLive` installation:

1. Make sure that `git` as well as the `make` and `curl` utilities are present on the system and enable `libxcrypt` compatibility for `glibc` library:

   <pre>sudo pacman -S git make curl libxcrypt-compat</pre>

2. Change into the `~/.local` directory:

   <pre>cd */.local</pre>

3. Download and unpack the installer:

   <pre>curl -L http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz | tar xz</pre>

4. Start installing with `I` and `↵` after entering the prompt:

   <pre>TEXLIVE_INSTALL_PREFIX=~/.local/texlive ./install-tl-*/install-tl</pre>

5. Append the install location to the path via the shell configuration file such as `~/.bashrc` or `~/.zshrc` in the home directory:

   <pre>echo 'export PATH="$HOME/.local/texlive/<i>yyyy</i>/bin/x86_64-linux:$PATH"' >> ~/<i>.shellrc</i></pre>

6. Close and restart the terminal before running the following configuring steps:

   <pre>tlmgr option autobackup -- -1<br>tlmgr option repository https://mirror.ctan.org/systems/texlive/tlnet<br>luaotfload-tool --update --force</pre>

7. Test the success by checking for responses from these commands:

   <pre>make<br>luatex<br>biber</pre>

8. Finally update the environment as follows:

   <pre>tlmgr update --self --all --reinstall-forcibly-removed</pre>
