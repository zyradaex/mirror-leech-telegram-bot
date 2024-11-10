<!DOCTYPE markdown>
<html>
<head>
</head>
<body>

<p>This README explains how to deploy the Mirror Leech Telegram Bot to Heroku using the <strong>deploy</strong> branch. Start by forking the repository <a href="https://github.com/zyradaex/mirror-leech-telegram-bot">here</a> and unchecking "Only fork master branch."</p>

<h2>Prerequisites</h2>
<ul>
  <li><strong>Heroku CLI</strong>: Ensure you have Heroku CLI installed. <a href="https://devcenter.heroku.com/articles/heroku-cli">Download Here</a></li>
  <li><strong>Git</strong>: Ensure Git is installed.</li>
</ul>

<h2>Steps to Deploy</h2>

<h3>1. Login to Heroku</h3>
<p>Login to your Heroku account using the following command in your terminal:</p>
<pre><code>heroku login</code></pre>

<h3>2. Clone the Repository</h3>
<p>Clone your forked repository and switch to the <code>deploy</code> branch:</p>
<pre><code>git clone -b deploy https://github.com/YOUR_USERNAME/mirror-leech-telegram-bot
cd mirror-leech-telegram-bot</code></pre>

<h3>3. Create a Heroku App</h3>
<p>Create a new Heroku app with container stack in the US region:</p>
<pre><code>heroku create your-app-name --stack=container --region=us</code></pre>

<h3>4. Set Environment Variables</h3>
<p>Copy the sample environment file and edit the variables:</p>
<pre><code>cp config_sample.env config.env</code></pre>
<p>Edit <code>config.env</code> to set the required variables:</p>
<ul>
  <li><strong>UPSTREAM_REPO</strong>: URL of the upstream repository</li>
  <li><strong>UPSTREAM_BRANCH</strong>: Branch name of the upstream repository</li>
  <li><strong>DATABASE_URL</strong>: URL of your database</li>
  <li><strong>BOT_TOKEN</strong>: Your bot's token</li>
  <li><strong>OWNER_ID</strong>: Your Telegram user ID</li>
  <li><strong>TELEGRAM_API</strong>: Your Telegram API ID</li>
  <li><strong>TELEGRAM_HASH</strong>: Your Telegram API hash</li>
</ul>

<h3>5. Add and Commit Changes</h3>
<p>Stage all changes and commit them with a message:</p>
<pre><code>git add . -f
git commit -m "Hello world"</code></pre>

<h3>6. Push to Heroku</h3>
<p>Deploy the <code>deploy</code> branch to Heroku by pushing it to the <code>main</code> branch on Heroku:</p>
<pre><code>git push heroku deploy:main</code></pre>

<h3>7. Scale and Monitor</h3>
<p>Once the deployment is complete, scale the application to run on Heroku:</p>
<pre><code>heroku ps:scale web=1</code></pre>

<p>To monitor your app logs, use:</p>
<pre><code>heroku logs --tail</code></pre>

<h2>Handling Private Files</h2>
<p>To manage private files in this branch, add the following files within this branch:</p>
<ul>
  <li><code>config.env</code></li>
  <li><code>token.pickle</code></li>
  <li><code>rclone.conf</code></li>
  <li><code>accounts.zip</code></li>
  <li><code>list_drives.txt</code></li>
  <li><code>cookies.txt</code></li>
  <li><code>.netrc</code></li>
  <li>or any other private file</li>
</ul>
<p>To delete a private file, simply add its name as a text message within this branch.</p>

<h2>Additional Notes</h2>
<ul>
  <li><strong>Stack</strong>: This setup uses the container stack to ensure the app runs in a Docker container environment.</li>
  <li><strong>Region</strong>: This app will be hosted in the <strong>US region</strong> on Heroku.</li>
</ul>

<p>Your app should now be up and running on Heroku!</p>

</body>
</html>