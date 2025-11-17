# Health Scorecard

A simple web app for tracking weekly health goals. Built this for dietitians and health coaches who need a quick way to score client progress and share results.

**Live version:** https://healthyscorecard.pages.dev/

## What it does

Tracks 5 health goals on a 0-2 point scale (10 points total):

- **Solid Breakfast** - protein & fiber before 10am, 5x weekly
- **Strength Training** - 3 workouts per week  
- **Cardio Goals** - 2 sessions weekly
- **Meal Logging** - photos and descriptions in app, 7 days
- **Quality Healthy Choices** - consistently good food choices

Plus a weekly check-in with 4 questions and space for notes.

## Why I built this

I wanted to be more results-oriented with my health goals. Instead of just tracking habits, I needed a rubric that would give me (and my nutritionist) a clear weekly score to see actual progress.

My nutritionist uses an app for meal tracking, and I wanted something that would work alongside that - a scoring matrix that could capture the bigger picture of my weekly health efforts. The output needed to be something she could easily copy into her app or send in messages.

This runs entirely in the browser - no data gets saved anywhere, which is perfect for client privacy.

## How to use it

1. Fill in names (optional)
2. Click the score buttons for each goal
3. Answer the check-in questions
4. Hit "Copy Results" - it goes to your clipboard AND shows in a text box
5. Paste wherever you need it

The output looks clean and professional:

```
WEEKLY GOALS
=======
Evaluator: Dr. Smith
Patient: John Doe
Solid Breakfast: 2 / 2
Strength Training: 1 / 2
Cardio Goals: 2 / 2
Meal Logging: 2 / 2
Quality Healthy Choices: 1 / 2

**Total Score: 8 / 10**

Quick Weekly Check-In:

Biggest win: Consistent morning routine
Main challenge: Finding time for strength training
What helped: Meal prep on Sundays
Next week focus: Schedule specific workout times
Dietitian Notes: Great progress. Focus on strength training consistency.
```

## Technical stuff

Just one HTML file with everything built in. No complicated frameworks, no confusing dependencies, no backend to worry about. Works on phones too.

### Deployment

This is hosted on CloudFlare Pages, which automatically deploys whenever I push to the main branch. It's free and reliable.

### Want to make your own version?

If you want to customize this for different goals or change the scoring, here's how:

1. **Fork this repo** on GitHub
2. **Edit the goals** in `index.html`:
   - Find the `<!-- Goal 1: Solid Breakfast -->` sections (there are 5 of them)
   - Change the goal titles, targets, and scoring descriptions to match your needs
   - Update the JavaScript `goalNames` object at the bottom to match your new titles
3. **Deploy to CloudFlare Pages**:
   - Go to [pages.cloudflare.com](https://pages.cloudflare.com)
   - Sign up/login with your GitHub account
   - Click "Create a project" → "Connect to Git"
   - Select your forked repo
   - Leave all settings as default (it's just static HTML)
   - Click "Save and Deploy"
   - Your site will be live at `yourprojectname.pages.dev`

Every time you push changes to GitHub, CloudFlare automatically redeploys. Takes about 30 seconds.

### Customizing the goals

The goals are defined in a few places in `index.html`:

1. **HTML sections** (around line 200+) - the visual goal boxes with `data-goal="goal1"` through `data-goal="goal5"`
2. **JavaScript objects** (around line 400):
   - `scores` - uses goal1, goal2, goal3, goal4, goal5
   - `maxScores` - points for each goal (currently all set to 2)
   - `goalNames` - display names used in the output

The structure is now generic (goal1, goal2, etc.) so you only need to change the display text and scoring options without worrying about breaking the JavaScript logic.

## Future ideas

Some things that could make this more useful:

- **Goal templates** - preset configurations for different types of health tracking (fitness focus, nutrition focus, medical recovery, etc.)
- **Progress tracking** - simple charts showing scores over time (would need some kind of data storage)
- **Custom scoring scales** - support for 0-3 or 0-5 point scales instead of just 0-2
- **Printable version** - CSS that formats nicely for printing physical copies
- **Multiple languages** - Spanish translation would probably be the most useful
- **Export formats** - save results as PDF or structured data formats
- **Goal categories** - organize goals into sections like "Nutrition", "Exercise", "Mental Health"
- **Reminder system** - simple way to schedule when to fill out the scorecard

Most of these would require adding complexity that goes against the current simplicity, so they'd need to be carefully considered. The whole point is that it works immediately without setup.

If you implement any of these, I'd be interested to see how they work out.

## Contributing

Found a bug or have an idea? Open an issue or submit a pull request. This is meant to be simple and useful.

## License

MIT License - use it however you want.
