# HOLA
 PONYYYY
gh repo clone aircrack-ng/aircrack-ng

	"name": "Aircrack-ng",
	"build": {
		"dockerfile": "Dockerfile",
		// Update 'VARIANT' to pick an Debian / Ubuntu OS version: debian-10, debian-9, ubuntu-20.04, ubuntu-18.04
		"args": {
			"VARIANT": "ubuntu-20.04"
		}
	},
	"runArgs": [
		"--cap-add=SYS_PTRACE",
		"--security-opt",
		"seccomp=unconfined"
	],
	// Set *default* container specific settings.json values on container create.
	"settings": {
		"terminal.integrated.shell.linux": "/bin/bash",
		"editor.formatOnSave": true,
		"clang-format.executable": "/usr/local/bin/clang-format",
		"clang-format.fallbackStyle": "none",
		"clang-format.assumeFilename": "${file}",
		"clang-format.style": "file",
		"editor.defaultFormatter": "llvm-vs-code-extensions.vscode-clangd",
		"clangd.path": "/usr/bin/clangd-10",
		"C_Cpp.clang_format_fallbackStyle": "none",
		"C_Cpp.clang_format_path": "/usr/local/bin/clang-format",
		"C_Cpp.clang_format_style": "file",
		"C_Cpp.formatting": "clangFormat"
	},
	// Add the IDs of extensions you want installed when the container is created.
	"extensions": [
		"ms-vscode.cpptools",
		"xaver.clang-format",
		"llvm-vs-code-extensions.vscode-clangd"
	],
	// Use 'forwardPorts' to make a list of ports inside the container available locally.
	// "forwardPorts": [],
	// Use 'postCreateCommand' to run commands after the container is created.
	"postCreateCommand": "pre-commit install --install-hooks",
	// Comment out connect as root instead. More info: https://aka.ms/vscode-remote/containers/non-root.
	"remoteUser": "vscode"
}