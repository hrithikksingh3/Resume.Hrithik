# Resume PDF email automation

The workflow at `.github/workflows/build-resume.yml` compiles `resume.tex` with XeLaTeX whenever you push a change to the resume source, then emails `resume.pdf` to `shrithik511@gmail.com`. The PDF is also retained for 30 days in the GitHub Actions run as an artifact.

## One-time GitHub setup

1. Create a GitHub repository and push this folder to it. GitHub only runs workflow files stored in the repository's `.github/workflows` directory.
2. In the repository, open **Settings → Secrets and variables → Actions → New repository secret**.
3. Add these secrets:
   - `MAIL_USERNAME`: the Gmail address that will send the PDF, for example `shrithik511@gmail.com`.
   - `MAIL_APP_PASSWORD`: a Gmail app password, not your normal Gmail password.
4. Enable two-step verification on that Gmail account, then create an app password for Mail in your Google Account security settings.
5. Push a change to any `.tex`, `.cls`, `.sty`, or font file. Open the repository's **Actions** tab to follow the first run.

## Changing the recipient

Edit the `to:` field in `.github/workflows/build-resume.yml` if you want the generated PDF sent to a different address.

## Notes

- A failed LaTeX build does not send an email, so you will not receive a broken PDF.
- Keep the two mail credentials only in GitHub Actions secrets. Do not place them in the workflow file or commit them to the repository.
