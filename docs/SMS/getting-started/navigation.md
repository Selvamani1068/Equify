# Signing In and Navigation

This chapter explains how to access the SMS module and how the navigation pane is organized, so that every later chapter can refer back to it without repeating the same steps.

## Signing in

Equify uses single sign-on (SSO) through your organization's identity provider. You do not create a separate Equify password.

1. Open the Equify URL provided by your administrator in a supported web browser.
2. If you are not already signed in to your organization's identity provider, you are redirected to your standard corporate sign-in page.
3. After authentication succeeds, Equify returns you to the application and opens the **Dashboard** by default.

If sign-in fails, confirm with your IT department that your account has been granted access to Equify, since access is provisioned centrally through the identity provider rather than inside the SMS module itself.

## The application shell

Once signed in, every screen in the SMS module shares the same layout:

| Area | Location | Purpose |
|---|---|---|
| Channel switcher | Top of the left rail | Switches between the **SMS** channel and other channels such as WhatsApp |
| Navigation menu | Left side of the screen | Lists every section of the SMS module: Dashboard, Control Centre, Routing Setup, Analytics, and Administration |
| Page header | Top of the main content area | Names the current screen and gives a one-line description of what it does |
| Main content area | Centre of the screen | The configuration form, table, or chart for the current screen |
| Notification banner | Bottom-left, occasional | Announces new platform features, such as a dashboard redesign |

## The navigation menu

The left-hand navigation menu is organized as a set of top-level sections, several of which expand to reveal sub-pages:

- **Dashboard** — a single screen, the default landing page after sign-in.
- **Control Centre** — expands to:
    - **Platform DB Setup**, which expands to **DB Configuration** and **DB Management**.
    - **Service Provider (SP)**, which expands to **SP Registration**, **SP Management**, and **Error Control Center**.
- **Routing Setup** — expands to **Traffic Management** and **Intelligent Routing**.
- **Analytics** — reporting and historical analysis screens.
- **Administration** — platform and user administration screens.

A small chevron (**>**) next to a menu item indicates that it expands into sub-pages. Selecting the parent item's text, or the chevron itself, expands or collapses that section without leaving the current screen.

!!! tip "Finding your way back"
    Every screen below the top level also shows a breadcrumb trail directly under the page header — for example **Dashboard › Traffic Management › Percentage Based** — so you always know exactly where you are, even several levels deep into a configuration screen.

## What's next

With sign-in and navigation covered, the next chapter walks through the **Dashboard**, the screen every user sees first and returns to most often.

Continue to [Dashboard Overview](../dashboard/index.md).
