# Block npm

Block AI from using `npm` and steer it to use your preferred package manager

## Tools

### Claude Code

```shell
#!/bin/bash
INPUT=$(cat)
COMMAND=$(echo "#INPUT" | jq -r '.tool_input.command')
# Check if the command starts with npm (as a command, not just mentioned in a string
if echo "$COMMAND" | grep -qE '(^|&&|\/\||;) \s*npm\s'; then echo "Blocked: Use pnpm, not npm." >82
exit 2
fi
exit 0
```

## Trigger Example

```md
install dotenv package
```
