# Security policy

*EasyView for PdfCraft is a third-party project and is not affiliated with PdfCraft or its authors; it only builds on their software.*

## Reporting a vulnerability

Please report it **privately**, not in a public issue.

Go to the **Security** tab of this repository, choose **Report a vulnerability**, and fill in the form. Only you and the maintainer can see the report.

Please include:

- what happens and why you think it is a security problem,
- the steps to reproduce it (the PDF or the keys and clicks that trigger it),
- the PdfCraft version and commit you applied the patch to, and your operating system.

You will get an acknowledgement as soon as I see the report. For a verified problem I aim to have a fix released within about 90 days, and I will tell you if it will take longer. If you want to be credited in the release notes, say so.

## Supported versions

Only the latest release gets security fixes. Please check that the problem is still there in the latest release before you report it.

## What is in scope

This repository is a **source patch** for PdfCraft (`patches/0001-viewer-mode.patch`): the viewer mode, its tab strip and its shortcuts. In scope:

- the code the patch adds or changes (anything in it that can crash PdfCraft, run code, or read or write files because of a crafted PDF or file name);
- the CI workflow and the files attached to a release (the patch and `SHA256SUMS.txt`).

## What is not in scope

A problem in PdfCraft itself (PDF parsing, rendering, editing, signing and so on) belongs to [storytold/pdfcraft](https://github.com/storytold/pdfcraft). If it also happens without this patch applied, please report it there.

## Disclosure

Please give me the time above before you publish details. When a fix is released I will publish a GitHub security advisory that names the affected versions.
