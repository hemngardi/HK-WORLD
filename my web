<script>
const { Octokit } = require('@octokit/octokit');
const { GitHubAuth } = require('github-auth');

// Replace with your GitHub username and password
const username = 'your-username';
const password = 'your-password';

// Create an instance of Octokit
const octokit = new Octokit({
  auth: {
    username,
    password,
  },
});

// Authenticate and get an access token using Octokit
octokit.auth({
  type: 'basic',
})
  .then((response) => {
    const accessToken = response.data.token;
    console.log(`Logged in successfully using Octokit! Access token: ${accessToken}`);
  })
  .catch((error) => {
    console.error('Error logging in using Octokit:', error);
  });

// Authenticate and get an access token using GitHubAuth
const auth = new GitHubAuth({
  username: 'your-username',
  password: 'your-password',
});

auth.login()
  .then((response) => {
    const accessToken = response.data.token;
    console.log(`Logged in successfully using GitHubAuth! Access token: ${accessToken}`);
  })
  .catch((error) => {
    console.error('Error logging in using GitHubAuth:', error);
  });
</script>
