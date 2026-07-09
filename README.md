# Skool to Tenant.so Migration Guide

> A complete guide for migrating your community from Skool to [Tenant.so](https://tenant.so) — covering members, courses, gamification, payments, and everything in between.

Skool made simplicity a feature, and for a lot of communities that was enough. But once you need a custom domain, events, real-time chat, an API, built-in email, or tiered pricing, Skool's single-plan model starts to feel like a ceiling. This guide walks you from Skool to Tenant.so without dropping members or momentum.

---

## Contents

- [Why Migrate](#why-migrate)
- [What You'll Save (or Gain)](#what-youll-save-or-gain)
- [Feature Comparison](#feature-comparison)
- [Migration Checklist](#migration-checklist)
- [Step-by-Step Guide](#step-by-step-guide)
- [Data Export from Skool](#data-export-from-skool)
- [Setting Up Tenant.so](#setting-up-tenantso)
- [Member Communication](#member-communication)
- [Post-Migration Checklist](#post-migration-checklist)
- [FAQ](#faq)
- [Support](#support)

---

## Why Migrate

### Where Skool Hits a Ceiling

Skool is a great starter platform. It runs out of room for growing communities in these specific ways:

- **No custom domain** - you're stuck on `skool.com/your-community`, which hurts brand and SEO
- **No events** - no built-in event pages, RSVPs, or reminders
- **No real-time chat** - feed and DMs only, no live chat rooms
- **No API** - you cannot automate signup, tagging, cross-platform sync, or integrations
- **No built-in email marketing** - you still need ConvertKit, Mailchimp, or Beehiiv
- **Single $99/mo plan** - no tiers, no freemium, no way to offer free access alongside paid
- **Limited gamification** - points and levels only, no streaks, badges, or leagues
- **No affiliate program** - no built-in referral tracking or payouts
- **Limited moderator tools** - coarse-grained permissions, no per-space roles
- **No white-labeling** - Skool branding is visible everywhere
- **Basic analytics** - no cohort retention, no funnel breakdown, no export

### What Tenant.so Adds

- Custom domain out of the box
- Built-in email marketing (replace ConvertKit or Mailchimp)
- Real-time chat powered by Ably
- Events with registration, reminders, and calendar sync
- Gamification: streaks, recognition badges, and leagues (in addition to points/leaderboards)
- AI-powered course assistant (Jarvis) with RAG over your course content
- Native Discord bot for cross-platform milestone alerts and slash commands
- Free member tier (freemium signup) with paywall-aware sidebar scoping
- Crypto (including Monero/XMR), BNPL, and ACH payments at 0% platform fee
- Affiliate program with built-in coupon and payout management
- Full REST/tRPC API for automation and integrations
- Multi-tenant architecture - run multiple communities from one account
- 31+ built-in integrations (replace Zapier)

---

## What You'll Save (or Gain)

Skool is only $99/mo, so the pure dollar savings depend on which tools you've bolted on top. Most Skool communities we've talked to are running a stack that looks like this:

| Current Skool Stack | Monthly Cost | With Tenant.so |
|---------------------|-------------|----------------|
| Skool | $99/mo | Included |
| ConvertKit or Mailchimp (email) | $79/mo | Included |
| Zapier (automation) | $49/mo | Included |
| Luma or Eventbrite (events) | $0-30/mo | Included |
| Discord bot dev/hosting | $10-50/mo | Included |
| **Total** | **$237-307/mo** | **One platform** |

**Annual savings: $2,844 - $3,684**

Beyond dollars, the bigger unlock is what you couldn't do at all on Skool: custom domain, API automation, tiered pricing, freemium funnels, and events without a second tool.

---

## Feature Comparison

| Feature | Skool | Tenant.so |
|---------|-------|-----------|
| Community feed | Yes | Yes |
| Online courses | Yes | Yes |
| Real-time chat | No | Yes |
| Events | No | Yes |
| Built-in email marketing | No | Yes |
| Custom domain | No | Yes |
| Gamification | Points + leaderboard | Points, streaks, badges, leagues |
| AI course assistant | No | Yes (Jarvis, RAG) |
| Native Discord bot | No | Yes |
| Free member tier | No | Yes |
| Tiered pricing | No (single $99/mo plan) | Yes |
| Affiliate program | Yes | Yes |
| DMs | Yes | Yes |
| Polls | No | Yes |
| Quizzes | No | Yes |
| Multi-tenant | No | Yes |
| API access | No | Yes |
| Crypto payments | No | Yes (incl. Monero) |
| BNPL / ACH | No | Yes |
| White-label | No | Yes |
| Platform fee | 0% | 0% |
| Mobile app | Yes | In beta (iOS submission) |

---

## Migration Checklist

### Pre-Migration

- [ ] Export your Skool member list (see [Data Export](#data-export-from-skool))
- [ ] Inventory your Skool community: sections, courses, key posts, links
- [ ] Screenshot your Skool community for reference (structure, branding)
- [ ] Save any course videos hosted directly on Skool (download originals)
- [ ] List your current integrations and workflows
- [ ] Register your custom domain (this alone is a big Skool → Tenant.so win)
- [ ] Note your current member count, active user count, and MRR

### During Migration

- [ ] Set up Tenant.so account and configure branding
- [ ] Point your custom domain at Tenant.so
- [ ] Recreate your space structure (groups → spaces)
- [ ] Import courses (sections, lessons, resources)
- [ ] Migrate key content (pinned posts, resource threads, FAQs)
- [ ] Configure email domain and welcome sequence
- [ ] Set up payment plans (mirror or expand beyond your $99/mo Skool tier)
- [ ] Enable gamification and pick your league cadence
- [ ] Test the full member experience end-to-end

### Post-Migration

- [ ] Send migration announcement to members
- [ ] Post migration notice inside your Skool community
- [ ] Update all external links (website, social bios, email signatures)
- [ ] Monitor signups for the first 2 weeks and follow up personally
- [ ] Cancel Skool after your grace period

---

## Step-by-Step Guide

### Step 1: Export Data from Skool

Skool's export options are more limited than Circle's. Expect to do more manual work here:

1. Go to **Settings → Members** and export your member list as CSV
2. Skool does not offer a full data export of posts, comments, or course content — you'll need to save these manually
3. For courses: download any videos you uploaded directly to Skool (external Vimeo/YouTube videos stay put)
4. Screenshot or copy-paste any pinned posts, resource lists, and FAQ threads

**Realistic expectation:** you'll get member emails cleanly. Everything else — posts, course text, discussion history — is more of a curation opportunity than a lossless migration. That's often a feature, not a bug.

### Step 2: Map Your Skool Structure to Tenant.so

| Skool Concept | Tenant.so Equivalent |
|---------------|---------------------|
| Community | Tenant |
| Classroom (courses) | Space (COURSE type) inside a Group |
| Discussion feed | Space (FEED type) |
| Levels / points | Recognition + Leagues |
| Members | Members |
| Admins | Admins |
| Moderators | Moderators (with fine-grained per-space roles) |

Skool has one feed; Tenant.so has many spaces you can group logically. Take advantage of that — this is the moment to give your community actual structure.

### Step 3: Set Up Tenant.so

1. **Create your community** at [tenant.so](https://tenant.so)
2. **Configure custom domain** — this alone justifies the move for most Skool users
3. **Set branding** — logo, colors, theme (Light, Dark, or Matrix)
4. **Create Groups and Spaces** — mirror your Skool feed/classroom split, then add what you couldn't have before (Events, Chat, Dashboards)
5. **Recreate courses** — sections, lessons, quizzes
6. **Configure payments** — Stripe with your existing account
7. **Set up email** — configure sending domain, welcome sequence
8. **Enable gamification** — pick your league schedule (weekly/monthly), configure recognition badges

### Step 4: Migrate Content

**Priority content to bring over:**
1. Course content (lessons, quizzes, resources) — this is the most valuable to preserve
2. Pinned posts and rules
3. "Start Here" and onboarding threads
4. Resource lists (tools, templates, links)

**What to leave behind:**
- Old day-to-day discussion threads (start fresh - it's healthier)
- Outdated announcements
- Old points leaderboards (Tenant.so's league system will regenerate rankings organically)

### Step 5: Migrate Members

Skool subscriptions are managed by Skool, not Stripe, so you cannot transfer subscriptions directly. Two options:

**Option A: Fresh Signup (Recommended)**
1. Export member emails from Skool
2. Send migration announcement (see templates below)
3. Members sign up on Tenant.so using a founding member link
4. Offer a launch discount matching or beating their Skool price ($79/mo instead of $99/mo is a strong signal)
5. Members cancel Skool once they're active on Tenant.so

**Option B: Overlap Period**
1. Run both platforms for 30-45 days
2. Post exclusively new content on Tenant.so
3. Post migration reminders on Skool
4. Sunset Skool after the overlap window

### Step 6: Redirect & Sunset

1. Update your custom domain DNS to point to Tenant.so (you probably didn't have one on Skool — take advantage now)
2. Post a final Skool announcement linking to your new community
3. Update every external link that pointed at `skool.com/your-community`
4. Keep Skool active for a 2-4 week grace period so stragglers can find the migration message
5. Cancel your Skool subscription

---

## Data Export from Skool

Skool's data export is limited compared to other platforms. Here's what you can and cannot pull out:

**Available:**
- Member list (email, name, join date) via Settings → Members → Export CSV
- Video files you uploaded directly (download from the classroom UI)

**Not directly available:**
- Full post + comment history
- Course text content (must be copy-pasted or scraped)
- Points/leaderboard history
- Direct messages
- Analytics history

**Workarounds:**
- For course content, log into Skool as an admin and copy each lesson's text/embeds into a doc
- For high-value discussion threads, screenshot or copy manually
- For member points/levels, decide whether to reset (recommended) or record the top members and grant equivalent recognition on Tenant.so

Treat the export limitations as forcing function to curate what's actually worth carrying over. Most communities have far more junk than gold in their post history.

---

## Setting Up Tenant.so

### Recommended Structure (for a typical Skool refugee)

**Groups:**
- Free Public Group - landing space + community-only content
- Members Group - courses, events, premium discussion
- (optional) VIP Group - coaching, mastermind, direct access

**Spaces inside Members Group:**
- General Discussion (FEED)
- Live Chat (CHAT) - the thing Skool couldn't do
- Weekly Events (EVENT)
- Course: [Your Signature Course] (COURSE)
- Resource Library (FEED, pinned)
- Wins & Accountability (FEED)

**Gamification setup:**
- Enable streaks (encourages daily return)
- Configure 5-10 recognition badges tied to milestones (first post, 30-day streak, course completion)
- Enable weekly leagues (mirrors the leaderboard behavior your Skool members are used to)

### Payments

Skool's flat $99/mo doesn't translate cleanly, so use the migration as a chance to redesign pricing:

- **Old:** flat $99/mo Skool
- **New:** free tier + $49-79/mo core + $149-199/mo premium (with courses, events, coaching)

You'll likely find the average revenue per member goes up, not down.

---

## Member Communication

### Announcement Email (Send 2 Weeks Before)

```
Subject: Big upgrade coming to our community

Hi [Name],

I'm moving our community from Skool to a platform that finally does everything
we've been wishing for: custom domain, real-time chat, live events, and built-in
email — all in one place.

Here's what you'll get:
- Real-time chat (not just feed replies)
- Events with reminders (no more "did anyone see this?")
- Streaks and badges (not just points)
- Course assistant that answers your questions from lesson content
- Your own custom-branded home (not skool.com/us)

What you need to do:
1. Click [this link] to claim your founding member spot
2. Use the same email you use today
3. Your access transfers, and you'll get a launch discount forever

New community goes live [DATE]. I'll keep Skool open for [DATE + 30 days]
so nobody gets left behind.

Reply if you have questions.

[Your name]
```

### Migration Post (Inside Skool)

```
🚀 We've moved!

Our community's new home: [LINK]

Everything you love is still here — plus real-time chat, live events, a course
assistant, and our own custom-branded home. This Skool will stay open for 30
more days for anyone still catching up, then it closes.

Come say hi: [LINK]
```

### Welcome Post (On Tenant.so)

```
Welcome to our new home! 🏠

Coming from Skool? Here's what's different:
- Chat is real-time now (check the Live Chat space)
- We have events with reminders (RSVP to the next one)
- You can earn streaks and badges (not just points)
- Jarvis, our course assistant, can answer questions about lessons

Update your profile, drop an intro in General Discussion, and check out the
Live Chat space — it's the thing Skool couldn't give us.

Glad you're here.
```

---

## Post-Migration Checklist

### Week 1
- [ ] Monitor signup rate - target 40%+ in the first week
- [ ] Personally welcome every new signup
- [ ] Post daily to maintain activity
- [ ] Send a reminder email to non-migrated members
- [ ] Fix any signup issues immediately

### Week 2
- [ ] Second reminder to non-migrated members
- [ ] Host your first live event on Tenant.so (the "we can finally do this" moment)
- [ ] Turn on gamification if you haven't already
- [ ] Gather feedback from migrated members

### Week 3-4
- [ ] Final reminder to remaining Skool members
- [ ] Post migration data (X% of active members moved)
- [ ] Cancel Skool
- [ ] Audit all external links (website, socials, email signatures)

---

## FAQ

### Will my members' Skool subscriptions transfer?
No. Skool manages billing internally, so subscriptions cannot be transferred directly. Members will sign up fresh on Tenant.so. Use this as an opportunity to offer a founding member discount — most communities see 60-80% of active members move within 30 days.

### How long does migration take?
Most Skool → Tenant.so migrations take 1-2 weeks of setup plus a 2-4 week member migration window.

### Can I migrate my Skool courses?
Yes. Course structure (sections, lessons) is recreated on Tenant.so. Text content needs to be copy-pasted since Skool doesn't offer course export. Video embeds (Vimeo, YouTube) stay put. Videos uploaded directly to Skool must be downloaded and re-uploaded.

### What about my points and leaderboard?
Points and leaderboards reset on migration — this is intentional. Tenant.so's league system regenerates rankings quickly. If you want to honor your top Skool members, grant them a founding recognition badge on Tenant.so.

### Do I need a custom domain?
No, but you should. It's one of the biggest reasons Skool users migrate. Tenant.so supports custom domains out of the box.

### What if some members don't migrate?
Expect 60-80% migration rate for active members. Inactive members typically don't migrate anywhere — that's normal.

### Can I keep Skool for the mobile app and use Tenant.so for everything else?
Not recommended. Splitting your community across two platforms doubles the moderation work and confuses members. Tenant.so's mobile app is in iOS submission and available in beta.

---

## Support

Need help with your migration?

- [Tenant.so Support Community](https://support.tenant.so)
- [Community Platform Comparison](https://github.com/Tenant-so/community-platform-comparison)
- [Circle to Tenant.so Migration Guide](https://github.com/Tenant-so/circle-to-tenant-migration)
- [Community Builder Toolkit](https://github.com/Tenant-so/community-builder-toolkit)

---

<p align="center">
  <a href="https://tenant.so">
    <img src="https://raw.githubusercontent.com/Tenant-so/.github/main/profile/tenant-logo.png" alt="Tenant.so" width="40" />
  </a>
  <br />
  <sub>Built by <a href="https://tenant.so">Tenant.so</a> — The Community Operating System</sub>
</p>
