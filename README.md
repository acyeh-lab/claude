## Running claude on computing cluster
- After logging into rhino, the standard way of starting claude is:
```
curl -fsSL https://claude.ai/install.sh | bash
```
- This will have to be run each time.
- Another way of doing this in a more intuitive manner is to include this in the ~/.bashrc file:
```
install_claude() {
    curl -fsSL https://claude.ai/install.sh | bash

    # Add to PATH only if not already present
    if ! grep -q 'export PATH="$HOME/.local/bin:$PATH"' "$HOME/.bashrc"; then
        echo 'export PATH="$HOME/.local/bin:$PATH"' >> "$HOME/.bashrc"
    fi

    # Apply to current session without sourcing entire .bashrc
    export PATH="$HOME/.local/bin:$PATH"
}
```
- And run
'''
install_claude()
''' 
