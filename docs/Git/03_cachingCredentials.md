# Caching your GitHub credentials in Git

If you're cloning GitHub repositories using HTTPS, we recommend you use GitHub CLI or Git Credential Manager (GCM) to remember your credentials.

## GitHub CLI

GitHub CLI will automatically store your Git credentials for you when you choose HTTPS as your preferred protocol for Git operations and answer "yes" to the prompt asking if you would like to authenticate to Git with your GitHub credentials.

- [x] Install GitHub CLI on macOS, Windows, or Linux.
- [x] In the command line, enter gh auth login, then follow the prompts.
    - When prompted for your preferred protocol for Git operations, select HTTPS.
    - When asked if you would like to authenticate to Git with your GitHub credentials, enter Y.
  
## Git Credential Manager

Git Credential Manager (GCM) is another way to store your credentials securely and connect to GitHub over HTTPS. With GCM, you don't have to manually create and store a personal access token, as GCM manages authentication on your behalf, including 2FA (two-factor authentication).

- [x] Install Git for Windows, which includes GCM. For more information, see Git for Windows releases from its releases page.

- [x] It is recommend always installing the latest version. At a minimum, install version 2.29 or higher, which is the first version offering OAuth support for GitHub.
- [x] The next time you clone an HTTPS URL that requires authentication, Git will prompt you to log in using a browser window. You may first be asked to authorize an OAuth app. If your account or organization requires two-factor auth, you'll also need to complete the 2FA challenge.
  
- [x] Once you've authenticated successfully, your credentials are stored in the Windows credential manager and will be used every time you clone an HTTPS URL. Git will not require you to type your credentials in the command line again unless you change your credentials.

!!! warning 

    Older versions of Git for Windows came with Git Credential Manager for Windows. This older product is no longer supported and cannot connect to GitHub via OAuth. We recommend you upgrade to the latest version of Git for Windows.






 