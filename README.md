# ru-humanize-skill

Скилл для русской вычитки агентских текстов: убрать канцелярит, лишние англицизмы, пустые связки и автогенерированную гладкость, не превращая текст в разговорный шум.

## Чтобы добавить себе

Попроси агента:

```text
Установи мне https://github.com/kvcop/ru-humanize-skill: прочитай README.md и skills/russian-humanize/SKILL.md, затем предложи, куда лучше добавить правила русского стиля — в мои глобальные или проектные AGENTS.md. Сохрани язык и стиль моих текущих инструкций, адаптируй формулировки под мои сценарии письма, покажи diff и только после моего подтверждения внеси изменения.
```

## Что это делает

`russian-humanize` работает не как отдельная команда, а как фоновое правило для агента. Если агент пишет длинный русский текст, документацию, Telegram-пост, голосовой сценарий или повествовательную заметку, он сам выбирает тон под задачу и прогоняет текст через русскую самопроверку.

Главная идея простая: не “добавить человечности”, а убрать мусор. В тексте остаются смысл, ритм и живые русские связки; идентификаторы, команды и устойчивые технические термины остаются как есть.

## Инструкции для агента

Перед установкой не редактируй инструкции молча. Сначала найди, где у пользователя лежат агентские правила: глобальный `AGENTS.md`, проектный `AGENTS.md`, `CLAUDE.md` или другой локальный файл. Спроси, можно ли добавить туда правила русского стиля.

Сохрани язык уже существующих инструкций. Если файл написан по-английски, добавь английский блок. Если по-русски, добавь русский. Если у пользователя основной сценарий не документация, адаптируй формулировки: для Telegram-постов говори про Telegram-посты, для TTS — про голосовой текст, для заметок — про повествовательную прозу.

В качестве референса можно использовать такой блок:

```markdown
- Before sending a Russian user-facing answer, do a short Russian-language pass:
  reread the answer as ordinary Russian prose and replace accidental
  English/Russian hybrids with natural wording.
- Apply the same pass before writing or committing Russian user-facing
  documentation, Telegram posts, voice scripts, reports, or narrative notes.
- Use Russian for descriptive technical prose.
- Keep English only when it is a stable literal identifier or an accepted
  technical name: file paths, commands, code symbols, env variables, package
  names, protocols, product names, and established terms.
- Avoid hybrid phrases in Russian chat and Russian docs. Prefer fully Russian
  wording unless the literal identifier itself is the subject.
- Use the `russian-humanize` skill for long Russian prose and any text that
  will be spoken aloud.
```

Потом положи сам скилл туда, где пользователь хранит локальные skills. Обычно достаточно скопировать папку `skills/russian-humanize`.

## Примеры

- [`references/reward-shaping.raw.md`](references/reward-shaping.raw.md) — нарочно гладкий AI-русский без второго прохода.
- [`references/reward-shaping.humanized.md`](references/reward-shaping.humanized.md) — тот же материал после применения правил.
- [`references/ai-coding-agents-context-engineering.raw.md`](references/ai-coding-agents-context-engineering.raw.md) — англо-русская смесь из технического поста про агентные рабочие процессы.
- [`references/ai-coding-agents-context-engineering.humanized.md`](references/ai-coding-agents-context-engineering.humanized.md) — тот же текст после русского прохода.

## Происхождение

Скилл сделан на основе идей и паттернов [`devswha/patina`](https://github.com/devswha/patina), но адаптирован под русскую прозу и агентские инструкции.

Дата создания первой версии: 01.04.2026. Паттерны с тех пор не обновлялись и могли устареть. Мы в основном проверяли сценарии с документацией, рабочими заметками и Telegram-сообщениями, поэтому какие-то жанры могут быть проработаны хуже.

Пул-реквесты с новыми русскими паттернами, примерами и аккуратными правками приветствуются.

## Лицензия

MIT.
