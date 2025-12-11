# Release Metrics Dashboard

A simple, client-side dashboard for visualizing product release metrics. No backend required - just HTML, CSS, and JavaScript!

## Features

- **Per-release overview**: Deep dive into individual release metrics
- **Comparative analysis**: Compare the last 10 releases side-by-side
- **Dynamic data loading**: Automatically reads from CSV file
- **Export functionality**: Export dashboards as PNG or PDF
- **Responsive design**: Works on desktop and mobile devices

## Setup on GitHub Pages

### Initial Setup

1. **Create a GitHub repository** (if you haven't already):
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Release metrics dashboard"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**:
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Source", select **Deploy from a branch**
   - Choose **main** branch and **/ (root)** folder
   - Click **Save**
   - Your dashboard will be available at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### Updating Data

To add new release data:

1. **Edit the CSV file** (`Release metrics.xlsx - release (summarised).csv`) directly on GitHub:
   - Click on the CSV file in your repository
   - Click the pencil icon (✏️) to edit
   - Add your new release row following the existing format
   - Click **Commit changes**

2. **Or update locally and push**:
   ```bash
   # Edit the CSV file locally
   git add "Release metrics.xlsx - release (summarised).csv"
   git commit -m "Add release 2025.4.3.0 metrics"
   git push
   ```

3. **Refresh the dashboard** - it will automatically load the new data!

## CSV Format

The CSV file should have the following columns (in order):

- `Release` - Release version (e.g., "2025.4.1.0")
- `Date` - Release date (format: M/D/YYYY)
- `MPR` - Major Product Release (TRUE/FALSE)
- `LXP bugs solved` - Number of LXP bugs solved
- `LXP ZD tickets solved` - Number of LXP Zendesk tickets solved
- `LXP SF associations solved` - Number of LXP Salesforce associations solved
- `ACM bugs solved` - Number of ACM bugs solved
- `ACM ZD tickets solved` - Number of ACM Zendesk tickets solved
- `ACM SF associations solved` - Number of ACM Salesforce associations solved
- `Total bugs solved` - Total bugs solved (sum of LXP + ACM)
- `Total ZD tickets solved` - Total Zendesk tickets solved
- `Total SF associations solved` - Total Salesforce associations solved
- `Bugs opened` - Total bugs opened
- `ZD tickets opened` - Total Zendesk tickets opened
- `SF associations opened` - Total Salesforce associations opened
- `Net new bugs created` - Net new bugs (opened - solved)
- `P2 within SLA` - P2 tickets resolved within SLA
- `P2 over SLA` - P2 tickets resolved over SLA
- `P3 within SLA` - P3 tickets resolved within SLA
- `P3 over SLA` - P3 tickets resolved over SLA

## Local Development

If you want to test locally before pushing to GitHub:

1. **Start a local server** (required because browsers block file:// access):
   ```bash
   python3 -m http.server
   ```

2. **Open in browser**:
   ```
   http://localhost:8000/index.html
   ```

## Sharing with Colleagues

1. **Give them access** to your GitHub repository (Settings → Collaborators)
2. They can:
   - View the dashboard at the GitHub Pages URL
   - Edit the CSV file directly on GitHub to add new releases
   - Or clone the repo and make changes locally

## Notes

- The dashboard automatically loads data from the CSV file on page load
- No server-side processing required - everything runs in the browser
- Data is read-only in the browser - to update, edit the CSV file on GitHub

