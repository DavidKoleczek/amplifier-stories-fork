# Bundle Activation Guide

This bundle has been renamed from `amplifier-stories` to `amplifier-module-stories`.

## Update Your Settings

Edit `~/.amplifier/settings.yaml` and change:

```yaml
bundle:
  active: amplifier-stories  # OLD
```

To:

```yaml
bundle:
  active: amplifier-module-stories  # NEW
```

## Restart Amplifier

After updating settings.yaml:

```bash
# Exit current session
exit

# Start new session
amplifier
```

## Verify Activation

In the new session, run:

```
"list available agents"
```

You should see 11 agents:
- storyteller (legacy, still works)
- story-researcher
- content-strategist
- technical-writer
- marketing-writer
- executive-briefer
- release-manager
- case-study-writer
- data-analyst
- content-adapter
- community-manager

## Alternative: Git URL Activation

If you want to keep the local development setup:

```yaml
bundle:
  active: git+file:///Users/michaeljabbour/dev/amplifier-stories@master
```

This loads from your local git repository directly.

## Troubleshooting

**"Bundle not found" error:**
- Check settings.yaml has correct bundle name
- Verify amplifier-module-stories is the active bundle
- Try git URL method if local path issues

**"Agents not loading" error:**
- Restart Amplifier session after settings change
- Check bundle.md has all agent paths correct
- Run "list available agents" to verify

**"Skills not found" error:**
- Verify ~/dev/anthropic-skills is cloned
- Check skills.dirs in settings.yaml
- Restart after adding skills configuration
