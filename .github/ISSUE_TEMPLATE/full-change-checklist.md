---
name: Full Change Checklist
about: An full checklist to be created as a blocking milestone issue when a release
  is proposed.
title: ''
labels: ''
assignees: ''

---

# The change checklist.

Must be formally executed for non-trivial releases.

## Analytics

  - [ ] GA property ID correct
  - [ ] custom dimensions and ecommerce metrics correctly reported
  
## SEO

  - [ ] page titles make sense!
  - [ ] no h2's used for anything other than section titles in an article
  - [ ] each article has exactly ONE h1 tag containing the title of the article

## Security

  - [ ] No pages echo back user input un-sanitised
  - [ ] All new raw SQL queries have been double checked for injection
  - [ ] No unsantised user input is eval'd
  - [ ] No unsantised user input is serialised or unserialised to json or other format
  - [ ] No files are written to disk
  - [ ] No source is included nor-imported out of the source tree or vetted deps
  - [ ] No use of `importlib` or other forms of programmatic import

## Data protection and legal

  - [ ] no static includes are hosted with unvetted 3rd parties, e.g. jquery, font-awesome, google-fonts
  - [ ] privacy policy is present, in the singular (i.e. old copies not still hanging around) and
    - [ ] signed off by legal
    - [ ] linked clearly from each and every form where users are asked for personal information
  - [ ] consent is retained for no longer than 30 days
  - [ ] other cookies are set for no longer than 30 days where consent has been obtained
  - [ ] redaction rules for private data are present for use in warehousing replica

## Accessibility

  - [ ] The site passes WCAG Level A https://www.w3.org/WAI/WCAG21/quickref/ specifically
    - [ ] Font-size, spacing and colour contrast of article content and major navigation
    - [ ] Navigation is reasonbly simple to navigate using a keyboard
    - [ ] Page can be scrolled by keyboard
    - [ ] Browser zoom works
    - [ ] All form controls are externally labelled
    - [ ] Form controls have programmatically identifiable sequences
    - [ ] Galleries are navigation and dismissible by keyboard
    - [ ] No custom controls 'trap' keyboard focus
    - [ ] CAPTCHA's have non-textual alternatives

## Performance

  - [ ] all GETs are deterministic (i.e. do not modify the database)
  - [ ] all new database methods have appropriate query caching
  - [ ] server side code depends on no new, unapproved cookies
  - [ ] client side storage uses LocalStorage, or similar mechanism, not cookies
  - [ ] performance regressions are documented and signed-off

## Monitoring

  - [ ] Uptime robot checks for each business-critical page type on the site, e.g. homepage, project portal
  - [ ] Schedule jobs have watchdogs
  - [ ] Dependent systems' health is monitored - DBs, message queues, etc

## BCP

  - [ ] New DBs are backed up following our best practices
  - [ ] Backups are monitored
  - [ ] Any impact that this change has on disaster recovery has been recognised and considered.

# BI

  - [ ] All DBs are available for dashboarding.


