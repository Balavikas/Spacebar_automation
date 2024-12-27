# Spacebar_automation

open terminal and cd desktop

Type following commands

```
mkdir run_spacebar

cd run_spacebar

vi auto_spacebar.sh
```

Press i

COPY AND PASTE the below code
```
#!/bin/bash

# File to be opened
FILENAME="empty_file.txt"

# Create an empty .txt file if it doesn't exist
touch "$FILENAME"

# Open the file with TextEdit
open -a TextEdit "$FILENAME"

# Function to handle stopping the script
cleanup() {
    echo "Exiting without saving..."
    # Close TextEdit without saving
    osascript -e 'tell application "TextEdit" to close every document without saving'
    exit
}

# Trap SIGINT (Ctrl+C) and call cleanup
trap cleanup SIGINT

# Simulate pressing spacebar every minute
while true; do
    sleep 60
    # Simulate pressing the spacebar in TextEdit
    osascript -e 'tell application "System Events" to keystroke " "'
done
```

press ESC

:wq!

Type following command

```
chmod +x auto_spacebar.sh

./auto_spacebar.sh
```



