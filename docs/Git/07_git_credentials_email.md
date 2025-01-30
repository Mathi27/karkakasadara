# Git Credentials & Email Management

If your Git is showing different credentials and you want to switch from one email ID to another for a specific repository or globally, follow these steps:

## 1. Update Git Email for a Specific Repository

Inside your repository, run:

```
git config user.email "your-new-email@example.com"
```

To verify:
```
git config --get user.email
```

## 2. Update Git Email Globally

If you want to change the email for all repositories:
```
git config --global user.email "your-new-email@example.com"
```

To verify:
```
git config --global --get user.email

```

## 3. Clear Cached Credentials (If Git Is Using Old Credentials)

If Git is using an old email linked to cached credentials, clear them:

=== "Mac/Linux"
    ```
    git credential reject https://github.com
    ```

=== "Windows (Credential Manager):"
    ```
    cmdkey /delete:git:https://github.com
    ```
Or manually go to Control Panel > Credential Manager > Windows Credentials and remove GitHub credentials.

## 4. Remove Stored Credentials

If you previously saved credentials in ~/.git-credentials, remove them:
```
rm ~/.git-credentials
git config --global --unset credential.helper
```

## 5. Log in with New Credentials

Once credentials are cleared, the next Git operation (push, pull, fetch) will ask for new credentials. When prompted, enter your correct GitHub/GitLab email and PAT (Personal Access Token if needed).

If using HTTPS authentication:

```
git push origin main
```

If using SSH, update the key:
```
ssh-keygen -t rsa -b 4096 -C "your-new-email@example.com"
```

Then add it to GitHub/GitLab.

## 6. Verify New Credentials in Commit History

To check if your new email is used in commits:

```
git log --pretty=format:"%h - %an <%ae>"
```

## 7. Change Email in Past Commits (If Necessary)

If you want to update your email in past commits, use:
```
git filter-branch --env-filter '
OLD_EMAIL="old@example.com"
CORRECT_NAME="Your Name"
CORRECT_EMAIL="your-new-email@example.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags

```
!!! warning 
       This rewrites history. Use only if necessary.

## 8. Test with a New Commit

Ensure everything is set correctly by making a test commit:

```
git commit --allow-empty -m "Testing new email"
git log -1
```

## 9. Push Changes to Remote (If Needed)
If you rewrote history in step 7, you must force-push:
```
git push --force origin main
```

!!! warning 
    Be cautious—this rewrites history for everyone.

If you frequently switch between multiple Git accounts, consider using SSH keys or different Git configurations per repository.
