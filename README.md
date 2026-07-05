# N Capital — Site Setup Notes

Everything below is placeholder content (name, logo initial, address, phone, email,
testimonial, founder name). Search-and-replace "Northbridge Capital" / "Northbridge
Capital Partners" and the "N" monogram once you've picked a real name.

## What's in here
- `index.html` — the entire site (HTML + CSS + JS in one file, no build step)
- `CNAME` — tells GitHub Pages which custom domain to serve on (edit this file first)

## 1. Put it on GitHub
1. Create a new repo on GitHub (Settings → New repository). Keep it Public.
2. Upload `index.html` and `CNAME` to the root of that repo (drag-and-drop on the
   GitHub web UI works fine, or `git add . && git commit -m "site" && git push`).

## 2. Turn on GitHub Pages
1. In the repo: **Settings → Pages**.
2. Under "Build and deployment", set Source = **Deploy from a branch**.
3. Branch = `main`, folder = `/ (root)`. Save.
4. Wait 1–2 minutes — GitHub gives you a URL like `https://yourusername.github.io/reponame`.
   Confirm the site loads there before touching DNS.

## 3. Point your existing domain at it
Edit the `CNAME` file in this repo and replace `yourdomain.com` with your actual
domain (e.g. `northbridgecapital.com` — no `https://`, no trailing slash).

Then, in your domain registrar's DNS settings (GoDaddy, Namecheap, Google Domains, etc.):

**If using the root/apex domain (`yourdomain.com`):**
Add four **A records** for `@` pointing to GitHub's IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**If using a subdomain (`www.yourdomain.com`):**
Add one **CNAME record**:
```
www  →  yourusername.github.io
```

Most people set up both: apex domain via the four A records, and a `www` CNAME,
then in GitHub Pages settings enter the apex domain as your custom domain and
check "Enforce HTTPS" once it's available (can take up to 24 hours for the
certificate to issue after DNS propagates).

## 4. Verify
- Repo → Settings → Pages should show your custom domain with a green checkmark.
- DNS changes can take anywhere from a few minutes to a few hours to propagate.
- Once it's live, tick "Enforce HTTPS" so the padlock shows.

## Things to personalize before this is "real"
- [ ] Business name + logo initial (search for "Northbridge" and the "N" monogram)
- [ ] Real email, phone, office address in the Contact section and footer
- [ ] Founder/advisor name + bio under "About"
- [ ] Testimonial quote
- [ ] The stats in the trust strip ($420M+, 18 yrs, etc.) — don't publish invented numbers
- [ ] Contact form: right now submitting it just shows an alert. Wire it to
      Formspree, Getform, or Google Forms (all free, no backend needed) so
      messages actually reach your inbox — GitHub Pages can't run server code.
- [ ] Footer disclosure paragraph — replace with real, accurate compliance language
      for a financial services business (this matters more than the rest of the copy)
