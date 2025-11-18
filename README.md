# Pixie Landing Page

## Deploying to GitHub Pages

### Step 1: Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial commit"
```

### Step 2: Create GitHub Repository

1. Go to [GitHub](https://github.com) and create a new repository
2. Name it `pixie-landing-page` (or any name you prefer)
3. **Do NOT** initialize it with a README, .gitignore, or license

### Step 3: Connect and Push

```bash
git remote add origin https://github.com/YOUR_USERNAME/pixie-landing-page.git
git branch -M main
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select:
   - **Branch**: `main`
   - **Folder**: `/ (root)`
5. Click **Save**

### Step 5: Access Your Site

Your site will be available at:
- `https://YOUR_USERNAME.github.io/pixie-landing-page/`

**Note**: The base path `/pixie-landing-page/` is already configured in your HTML files, so make sure your repository name matches this path, or update the base path in your build configuration if you use a different repository name.

## Setting Up Custom Domain (trypixie.app)

### Step 1: Configure DNS on Namecheap

1. Log in to your [Namecheap account](https://www.namecheap.com/)
2. Go to **Domain List** and click **Manage** next to `trypixie.app`
3. Go to the **Advanced DNS** tab
4. Add the following DNS records:

   **For Apex Domain (trypixie.app):**
   - Type: `A Record`
   - Host: `@`
   - Value: `185.199.108.153`
   - TTL: `Automatic`
   
   - Type: `A Record`
   - Host: `@`
   - Value: `185.199.109.153`
   - TTL: `Automatic`
   
   - Type: `A Record`
   - Host: `@`
   - Value: `185.199.110.153`
   - TTL: `Automatic`
   
   - Type: `A Record`
   - Host: `@`
   - Value: `185.199.111.153`
   - TTL: `Automatic`

   **OR use CNAME (Recommended for subdomains):**
   - Type: `CNAME Record`
   - Host: `@` (or `www` for www.trypixie.app)
   - Value: `guru3s.github.io`
   - TTL: `Automatic`

   **Note**: For `.app` domains, you typically need to use A records for the apex domain. If you want `www.trypixie.app` to work, add a CNAME record with Host: `www` pointing to `guru3s.github.io`.

### Step 2: Configure GitHub Pages

1. The `CNAME` file has already been created in this repository with `trypixie.app`
2. Go to your GitHub repository → **Settings** → **Pages**
3. Under **Custom domain**, enter: `trypixie.app`
4. Check **Enforce HTTPS** (this will be available after DNS propagates)
5. Click **Save**

### Step 3: Wait for DNS Propagation

- DNS changes can take 24-48 hours to propagate, but usually work within a few hours
- You can check DNS propagation using [whatsmydns.net](https://www.whatsmydns.net/)
- Once DNS is propagated, GitHub will automatically enable HTTPS for your domain

### Step 4: Verify

After DNS propagates, your site will be available at:
- `https://trypixie.app`

**Important**: The site has been configured to work with the custom domain (paths updated from `/pixie-landing-page/` to `/`).

### Alternative: Deploy from `/docs` folder

If you prefer to keep your source code in the repository and only deploy the built files:

1. Move all files to a `docs` folder
2. In GitHub Pages settings, select **Source**: `main` branch, `/docs` folder
3. Your site will be available at the same URL

