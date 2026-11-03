# ADHD-Manager: scope, draft 1 (2026-10-30)

School project. First users: Vadim and Eric only. Vadim writes the logic, Claude does setup and hard UI with teaching comments, Eric tests as a real user.
The app helps with ADHD problems. It does not treat them, and it says so on screen.

Due date: not set yet. The freeze date comes from it.

## Must (the first version)

1. **Accounts.** Sign up, log in, and each person sees only their own data.
2. **Short questionnaire.** About 8 questions that pick which problems you get help with, and your goal.
3. **Tasks on a lightweight timeline.** A calm line that shows only what is near. Each task has a "smallest first step" field.
4. **Need-help button** with these options:
   - I can't start
   - I'm stuck scrolling or gaming
   - I can't sleep
   - I feel ashamed
   - I'm in crisis (crisis lines always visible)
   Each one shows a short technique, a personal reassurance line and your goal. The linked source sits in the bottom right corner.
5. **ADHD test link** with the advice not to self-diagnose and to see a practitioner if the score is high.
6. **ADHD-oriented design** throughout: one main action per screen, few colours, nothing flashing.

Done means: Vadim and Eric each use it for 3 days, neither can read the other's data, and every help text has a real source.

## If time

- Day schedule
- Reminders while the site is open
- Wind-down reminder at bedtime (Eric's sleep problem)
- Date tracker
- Organised notes

## Bonus

- Practitioner sharing, as a summary you export and hand over yourself (no live access)
- Reminders when the site is closed. These need push notifications and a server to send them
- Personalised pop-ups and quotes beyond the help button
- Public launch and the .com domain

## Decisions already made (say if you want any changed)

- **Stack:** plain HTML, CSS and JS modules, like VELM Searcher, with Supabase for accounts and the database. GitHub Pages hosts it.
- **Security:** Row Level Security on every table. No real personal notes go in until a test proves one account can't read the other's data.
- **"Date tracker"** is read as countdowns to important dates. Correct this if you meant something else.
- **Repo:** its own Git repo, not inside the VELM Searcher one.

## Facts checked 2026-10-30

- Supabase Free: 2 active projects, 500 MB database, 50,000 monthly active users, paused after 1 week of inactivity. Open the app in the days before a presentation.
- The Supabase publishable key can be public; only Row Level Security protects the data. The secret key never goes in the browser or the repo.
- On iPhone, web push only works after the site is added to the home screen (iOS 16.4+). Reliable reminders with the app fully closed are unconfirmed; test on a device before promising them.
