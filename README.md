# ssh-remote-script
Action that runs script on ssh remote

## Usage
```
runs-on: ubuntu-latest
steps:
  - name: Run script on remote
    uses: baikaldigitalacademy/ssh-remote-script@v1
    with:
      private-key-file: ${{ secrets.SSH_PRIVATE_KEY }}
      user: ${{ secrets.SSH_PRIVATE_USER }}
      host: ${{ secrets.SSH_REMOTE_HOST }}
      # bash script to execute on remote
      run: |
        echo "Test script running on remote" > /tmp/ssh-remote-script.txt
        echo "Trying multiline script" >> /tmp/ssh-remote-script.txt
        echo "this code appends lines to file" >> /tmp/ssh-remote-script.txt      

  - name: Run single command on remote
    uses: baikaldigitalacademy/ssh-remote-script@v1
    with:
      private-key-file: ${{ secrets.SSH_PRIVATE_KEY }}
      user: ${{ secrets.SSH_PRIVATE_USER }}
      host: ${{ secrets.SSH_REMOTE_HOST }}
      # bash command to execute on remote
      run: echo "Single running on remote" >> /tmp/ssh-remote-script.txt
```
