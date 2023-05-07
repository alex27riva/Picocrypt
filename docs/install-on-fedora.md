# How to install Picocrypt on Fedora from source
- ### Install required packages
	- `sudo dnf install -y golang-bin libXxf86vm-devel`
- ### Clone the repository  
	- `git clone https://github.com/HACKERALERT/Picocrypt.git`
- ### Compile  
	- `cd Picocrypt/src`
	- `go build -ldflags="-s -w" Picocrypt.go`
- ### Install  
	- `cp Picocrypt ~/.local/bin/picocrypt`
- Copy icon  
	- `cp ../images/key.svg ~/.local/share/icons/picocrypt.svg`
- ### Create desktop entry  

  ``` bash
  cat << EOF > ~/.local/share/applications/picocrypt.desktop
  [Desktop Entry]
  Type=Application
  Version=1.0
  Comment=A very small, very simple, yet very secure encryption tool.
  Categories=Tools
  Terminal=false
  Exec=/home/${USER}/.local/bin/picocrypt
  Name=Picocrypt
  Icon=/home/${USER}/.local/share/icons/picocrypt.svg
  EOF
  ```