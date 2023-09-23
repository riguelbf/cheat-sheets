# Generating a token

Generate a token using the instructions from [Creating a personal access token](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token). (GitHub profile -> Settings -> Developer Settings -> Personal access tokens)

# Actually using the token

## If you already have the repository cloned locally
git remote remove origin
git remote add origin https://[TOKEN]@github.com/[REPO-OWNER]/[REPO-NAME]
git push

## If you are cloning a new repository
git clone https://[TOKEN]@github.com/[REPO-OWNER]/[REPO-NAME]