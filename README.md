# IronQ Coach

IronQ Coach turns Claude into a strength coach. It pairs the IronQ connector with five coaching routines, so that when you ask "how did my training go this week?" Claude knows which numbers to read, how to compare them, and how to finish with one clear thing to do next.

## What it does

| Routine | Ask something like | Needs an IronQ account? |
|---|---|---|
| Weekly training review | "How did my training go this week?" | Yes |
| Strength progress | "Am I still getting stronger on leg press?" | Yes |
| Next session prep | "What weights should I use today?" | Yes |
| Cut without losing muscle | "I'm 225 lb and want to get to 205 without losing strength." | No |
| Weight plateau check | "My weight hasn't moved in three weeks. Is this a plateau?" | No |

The two fat-loss routines work for anyone, straight away. The three training routines read your own workout log from the IronQ iPhone app. The first time you ask about your own training, Claude shows a Connect button; sign in to IronQ and tap ALLOW.

## Setup

1. Add the plugin from Customize > Plugins in Claude.
2. Open the plugin's Connectors tab and connect IronQ (`https://ironq.app/mcp`).
3. Ask one of the questions above.

## Privacy

Access to your workout log is read-only: IronQ's database refuses any change made through the connector. IronQ never receives your conversation and never reads Claude's memory, chat history or files. The only thing that saves anything is building a Cut Plan, which stores the plan so its code can be claimed in the app later.

- Privacy policy: https://ironq.app/privacy
- Terms: https://ironq.app/terms
- Help: https://ironq.app/connect/claude

IronQ Coach does not give medical advice and never gives medication or dosing advice.

## License

MIT. See `LICENSE`.
