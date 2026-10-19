# SSH on Linux

Generate a new SSH key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Create a config file in the .ssh folder:

```bash
touch ~/.ssh/config
chmod 600 ~/.ssh/config
```

Add your host configuration to the config file:

```
Host <your.host.nickname>
	HostName <your.host.endpoint>
	User git
	IdentityFile ~/.ssh/<key_name>
	AddKeysToAgent yes
	IdentitiesOnly yes
```

Start the ssh-agent in the background:

```bash
eval "$(ssh-agent -s)"
```

Test your connection:

```bash
ssh -T <your.host.nickname>
```
