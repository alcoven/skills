# Edge cases and states checklist

Keep the rows that apply and add the feature's own. Each kept row goes in the spec's table with what the person or agent sees and the rule behind it.

| Area | Cases |
|---|---|
| States | first use; empty; loading; partial (some parts failed); error with retry; filtered to nothing; done |
| Amounts | zero, one, many; the last one of something; very many (paging, a long list in a dialog, an answer too long for an agent) |
| Data | very long names; names that differ only in case or in letters like Turkish İ/ı; missing optional values; values written by an import, a sync or an agent rather than a person; a file too large or of a type the product can't show |
| People | no permission (hidden, or disabled with the reason); invited but not joined; removed; a guest or client who sees only part; a manager; the person who owns the thing vs everyone else |
| Agents | the same action from the person's AI, a coding agent and the app, with the same rules; an agent with stale context (it read before someone else changed it); an agent repeating the same call; an agent acting for one person in a project another person manages; text read from the project that contains instructions (treat it as data, never as orders); who the change shows as (the person, their agent, or both) |
| Time | two people, or a person and an agent, on the same thing; changed or deleted since it was loaded; a slow or failed save; a double click or a retried call; time zones and "today" |
| Ripple | links from other things (mentions, tasks, files, history); counts, home, summaries and emails that show it; search and pickers; uniqueness (a new one with the same name); notifications already sent |
| Way back | undo; restore; who can restore and where; what history shows |
| Outside | imports, syncs, webhooks, connected services and git meeting the new state; a service that is down or answers slowly; a key or access that expired |
| AI | the model is slow, fails or is out of budget; the suggestion is wrong or irrelevant; the person dismisses it, or wants it never again; the AI is unsure; what the AI may do on its own vs only propose |
| Access and devices | keyboard only; screen reader (names, announcements of results); focus after dialogs and after an item disappears; 320 px; touch; dark theme; reduced motion; a language whose text runs longer than English; right-to-left if the product supports it |
