# PHQ-9 classroom page

A self-scoring web version of the Patient Health Questionnaire (PHQ-9) for the Disorders and Therapies unit in Psych 100. It's a single file (`index.html`) with no build step, so it runs as is on GitHub Pages.

## Privacy

Everything runs in the student's browser. Answers are never saved or sent anywhere, and refreshing the page clears them.

## How students use it

Students first choose who they're answering for:

- **Myself.** Students answer the nine items about their own last two weeks.
- **A case study.** Students answer for the person described in a paper case study handed out in class. They can type the person's name (optional), and the questions and results will use it. If they leave it blank, the page says "this person." Switching between the two modes clears any answers on the page.

After answering all nine items (and, optionally, the unscored difficulty item), students select **Calculate score**. If any items are unanswered, the page highlights them and asks students to finish.

## What the results show

- **Total score** (0–27) on a scale showing the five severity ranges: minimal (0–4), mild (5–9), moderate (10–14), moderately severe (15–19), and severe (20–27).
- **What usually happens next in a clinic.** These are the treatment actions the PHQ-9's developers proposed for each range, from watchful waiting to counseling, medication, and specialist referral.
- **Score versus symptom pattern.** A table matches each item to its DSM-5 criterion for major depressive disorder and shows whether the answers meet the categorical algorithm. The algorithm requires five or more symptoms at "more than half the days" or more (item 9 counts at any level), including depressed mood or loss of interest.
- **Difficulty functioning.** Item 10 is reported but not added to the total, and is tied to DSM-5 criterion B (clinically significant distress or impairment).
- **Think about it.** Three discussion questions.
- **Print or save as PDF**, for students who need to turn in their results. In case study mode, the printout includes the case name.

## Support resources and item 9

Every page shows a support line in the footer with 988 (call or text) and a link to [St Ignatius Wellness Counseling](https://sites.google.com/siprep.org/wellness/home).

When a student answering for **themselves** gives any response above "Not at all" on item 9 (thoughts of being better off dead or of self-harm), a support message appears at the top of the results. It includes 988, St Ignatius Wellness Counseling, and 911 for immediate danger. In **case study** mode, the same response shows a teaching note instead, explaining that this prompts a same-day safety assessment in clinical practice.

## Customizing

All settings are in the `CONFIG` object at the top of the script near the bottom of `index.html`:

| Setting | What it does |
| --- | --- |
| `includeItem9` | `true` (default) uses the PHQ-9. `false` switches to the PHQ-8, which drops item 9, keeps the same cutoffs (maximum score 24), and updates the title and citation. |
| `counseling.name` | Name shown in support messages. Currently "St Ignatius Wellness Counseling." |
| `counseling.url` | Link for the counseling name. Currently https://sites.google.com/siprep.org/wellness/home. |
| `counseling.phone` | Optional phone number shown after the name. Currently blank. |
| `allowCaseMode` | `true` (default) shows the "A case study" option. `false` hides it so students can only answer for themselves. |

## Hosting on GitHub Pages

Put `index.html` (and this README) in a folder in your Pages repository, for example `/phq9/`. The page will be available at `https://<username>.github.io/<repo>/phq9/`.

## Attribution

The PHQ-9 was developed by Drs. Robert L. Spitzer, Janet B. W. Williams, Kurt Kroenke, and colleagues, with an educational grant from Pfizer Inc. No permission is required to reproduce, translate, display, or distribute it.

Kroenke, K., Spitzer, R. L., & Williams, J. B. W. (2001). The PHQ-9: Validity of a brief depression severity measure. *Journal of General Internal Medicine, 16*(9), 606–613.

This page is for classroom learning. A PHQ-9 score is a screening result, not a diagnosis.
