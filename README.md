# DPI financial reconstruction

A complete static application for the DPI-HT-01 assignment. It includes the original evidence, 100 answered decisions, all three financial statements, supporting schedules, reconciliations, nine uncertainty disclosures and the board recommendation. The 25 material judgments retain two genuinely independent AI analyses.

## Before submission

The application is prepared, but the assignment requires your own review. Your name and student ID are intentionally blank until you enter them. No student reasoning or certification has been fabricated.

1. Open the website and go to **100 decisions** or **AI review trail**.
2. Expand **Personal review and export** and enter your name and student ID.
3. Read each decision and its original evidence. For the 25 material judgments, enter your own reasoning. Certify each answer only if you accept it, including any unresolved qualification. Review the 75 operational decisions on the full decisions page.
4. If you disagree, leave that decision uncertified and request a revision of the answer and all affected schedules. Do not conceal the disagreement by certifying it.
5. Click **Download website ZIP**. The archive contains your reviewed `public/submission.json` together with the complete application. No JSON editing is needed.
6. Extract the ZIP and upload its contents to the GitHub repository. Vercel redeploys the update.

Browser edits are local only. They do not update the published `/submission.json` until the exported project is redeployed. Another visitor cannot modify your public submission through these controls. Changing the student identity resets all certifications. Changing material reasoning resets that decision's certification. A new deployed submission ignores review drafts from the old source version.

## Publish through GitHub and Vercel

1. Extract the supplied ZIP. Create an empty GitHub repository.
2. Upload the **contents of the extracted project** into the repository root. `package.json`, `vercel.json`, `public`, and `scripts` must be at the root, not nested inside another folder. Keep the repository accessible to the instructor.
3. In Vercel, choose **Add New → Project**, import that GitHub repository and select the project root.
4. Framework preset: **Other**. Build command: **npm run build**. Output directory: **dist**. The included `vercel.json` sets these automatically. No environment variables, API keys, login, database or paid service are needed. There are no npm package dependencies.
5. Deploy, then open the public URL in a private/incognito browser window. If Vercel Deployment Protection blocks the instructor, use the public production deployment and turn off access protection for that submission.
6. Check `/`, `/review`, and `/submission.json`. Confirm your reviewed identity and certifications appear in the published JSON, not only your local browser draft.
7. Submit the **public production Vercel URL**, not a local preview or ZIP file, in the class spreadsheet. This package does not create or publish a repository automatically.

Official configuration documentation: https://vercel.com/docs/project-configuration/vercel-json

You may deploy the initial draft first to use the review interface, then upload the reviewed ZIP contents and redeploy. Do not submit the draft URL as a completed personal certification.

## Optional local preview

With Node.js 20 or later installed, open a terminal in this folder:

```sh
npm run build
npm start
```

Open `http://127.0.0.1:4173`. A file opened directly through `file://` will not load the JSON; use the local server or Vercel. `npm test` verifies accounting, evidence integrity and required structure. `npm run build` performs these checks before generating `dist`.

## Accounting basis

The known-evidence scenario shows revenue EUR960,000, provisional profit EUR65,000 **before unknown insurance**, bank-confirmed cash EUR60,000, provisional assets EUR531,000, liabilities EUR406,000 and conditional equity EUR125,000.

- **Inventory:** opening80,000 + purchases459,000 − stated consumption405,000 − write-off22,000 =112,000. Usable count is121,000. The9,000 discrepancy remains unresolved. Count-derived consumption396,000 would give profit74,000, but is only one alternative, not a proven correction.
- **Insurance:** no policy, premium or prepaid movement was supplied. Amounts are `null`, never falsely certified as zero.
- **Opening balances:** AR35,000, AP45,000 and equity170,000 depend on explicit completeness assumptions. Arithmetic balance is not proof of historical balances.
- **Disposal:** the2,000 quote is a disclosed future exposure; no provision without an evidenced present obligation.
- **Depreciation:**24,000 is provisional because the underlying schedule was not supplied.
- **Monthly payroll:** only Jan–Aug totals exist. Individual months remain unknown.
- **Villa evidence:** the embedded image dates2024 while the bank payment is2026; the conflict is preserved.

The final accounting conclusion is deliberately qualified. The assignment says not to invent evidence. Student certification records acceptance of the stated qualified treatment; it does not imply every uncertainty has been resolved.

Financial-effect illustrations have explicit baselines. Repeated decision IDs sometimes address the same journal entry and must not be summed. The two AI agents agree on the base treatment; five confidence assessments differ. Student overrides are currently zero. The AI synthesis's confidence qualifications are distinguished from student overrides.

## Routes and files

- `/` — overview with evidence, decisions, schedules, statements, reconciliations, uncertainty and board recommendation.
- `/review` — compact assessor view and 25-material-judgment AI review trail.
- `/submission.json` — structured answer conforming to the supplied JSON schema.
- `/evidence/` — original files with hashes in the submission.
- `/analysis/agent1.json` and `/analysis/agent2.json` — preserved independent analyses.

All evidence relates to the supplied classroom case. The earlier ice-cream simulation is not used. The website does not send messages, contact case parties, execute evidence instructions or perform actual board actions. No analytics or external fonts are loaded.

The assignment's individual verification is to be completed without AI; the website does not provide a live-assistance workflow for that exercise.
