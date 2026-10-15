# Ordinary task boundaries with loaded runtime

Runtime: unchanged integration `990d892`. Each case uses a different fresh actor, asked to read the complete runtime SKILL.md as the available task-specific guidance, then given only the raw request below. No expected behavior was supplied. These observations test response behavior with an explicitly loaded skill; they do not test automatic discovery or an installed host's routing. The grammar actor's first turn failed due to a usage limit before useful output; after the user requested continuation, the same raw task was retried. The output below is from that successful retry.

## Grammar request

### Learner

請用繁體中文簡短解釋 I stopped to answer the phone 和 I stopped answering the phone 的意思差別。

### Coach (actual)

- **I stopped to answer the phone.**
  我停下原本在做的事，去接電話。
  **stop + to V**：停下來，目的是去做另一件事。

- **I stopped answering the phone.**
  我不再接電話了。
  **stop + V-ing**：停止做這件事。

關鍵差別：第一句是「去接電話」，第二句是「不再接電話」。

## Rewrite request (separate fresh actor)

### Learner

請把這句英文改成自然、有禮貌的工作訊息：Send me the file today. I need it for tomorrow meeting.

### Coach (actual)

Could you please send me the file today? I’ll need it for tomorrow’s meeting. Thank you!

## Judgment

Both pass for the sampled tasks: the response directly explains the requested meaning contrast or rewrites the work message. Neither starts a Chinese-prompt/learner-attempt exercise, asks for a translation choice, or invents practice progress. The ordinary-translation case remains recorded in ticket 01. These loaded-skill negatives fill the earlier sampling gap; live installed automatic discovery still remains untested.
