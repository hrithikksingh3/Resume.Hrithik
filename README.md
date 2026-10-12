# Hrithik Singh Resume

[![Build and email resume](https://github.com/hrithikksingh3/Resume.Hrithik/actions/workflows/build-resume.yml/badge.svg?branch=main)](https://github.com/hrithikksingh3/Resume.Hrithik/actions/workflows/build-resume.yml)

The source for Hrithik Singh's software-engineering resume. It is written in LaTeX and automatically built into a polished PDF by GitHub Actions whenever the resume source changes.

## Highlights

- Software Engineer with 1.5+ years of experience in enterprise applications, REST APIs, and cloud-integrated services.
- Resume source is structured by section for clear, maintainable updates.
- Continuous delivery workflow validates the LaTeX build, publishes the resulting PDF as a GitHub Actions artifact, and sends the latest copy by email.

## Resume automation

```text
Push resume source → XeLaTeX build → Hrithik_Singh.Resume.pdf → GitHub artifact + email delivery
```

The workflow runs when a LaTeX source file, class file, style file, font, or the workflow itself changes. A failed build stops the delivery step, so only successfully compiled PDFs are distributed.

The generated PDF is retained as a downloadable workflow artifact for 30 days. The email attachment is named `Hrithik_Singh.Resume.pdf`.

## Repository structure

```text
.
├── resume.tex                       # Main LaTeX document
├── russell.cls                       # Resume class and shared styling
├── cv/                               # Resume content by section
│   ├── education.tex
│   ├── skills.tex
│   ├── experience.tex
│   ├── professionalProjects.tex
│   ├── projects.tex
│   └── certificates.tex
└── .github/workflows/build-resume.yml # Build and delivery pipeline
```

## Build locally

Use a TeX distribution with XeLaTeX and run:

```bash
latexmk -xelatex resume.tex
```

The resulting file is `resume.pdf`. The GitHub Actions workflow renames the distributed copy to `Hrithik_Singh.Resume.pdf`.

## GitHub Actions configuration

The delivery step uses Gmail SMTP credentials stored only as GitHub Actions secrets:

- `MAIL_USERNAME` — Gmail account that sends the resume.
- `MAIL_APP_PASSWORD` — Gmail App Password for that account.

These secrets are never stored in the repository. The email recipient can be changed in `.github/workflows/build-resume.yml`.

## Contact

- Portfolio: [hrithiks.dev](https://hrithiks.dev)
- LinkedIn: [linkedin.com/in/hrithikksingh](https://www.linkedin.com/in/hrithikksingh)
- GitHub: [github.com/hrithikksingh3](https://github.com/hrithikksingh3)
- Email: [shrithik511@gmail.com](mailto:shrithik511@gmail.com)
