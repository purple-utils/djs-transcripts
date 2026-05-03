<div align="center"><h1>ᓚᘏᗢ djs-transcripts</h1></div>
> [!IMPORTANT]
> This repository was forked from [aymenelouadi/discord-transcripts-v2](https://github.com/aymenelouadi/discord-transcripts-v2) and modified for the use of Purple Utilities.
---
This version of `djs-transcripts` is purposed for the **Purple Utilities** project. This features the latest up-to-date exporting system of **Components v2**, an enhanced version of exporting normal messages, and more advanced systems that allow you to freely choose how to export.

## Quick Start
<h3>`createTranscript` - Generate from a live channel</h3>
```javascript
import { createTranscript, ExportReturnType } from '@purple-utils/djs-transcripts';

// Export as a Discord attachment (default)
const attachment = await createTranscript(channel);
await logChannel.send({ files: [attachment] });

// Export as a string and save to disk
const html = await createTranscript(channel, {
  returnType: ExportReturnType.String,
  filename: 'transcript.html',
  saveImages: true,
  poweredBy: true,
});
```
<h3>`generateFromMessages` - Generate from an array of messages</h3>
```javascript
import { generateFromMessages, ExportReturnType } from '@purple-utils/djs-transcripts';

const messages = await channel.messages.fetch({ limit: 100 });

const buffer = await generateFromMessages(messages, channel, {
  returnType: ExportReturnType.Buffer,
  saveImages: false,
});
```

Any contributions are welcomed. The only requirement is that you must specify whether AI was used within your contribution or not. Use of AI within your contribution will result in it being denied upon detection.