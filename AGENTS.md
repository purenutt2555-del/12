<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

## Application architecture
- Keep shared site navigation and footer in the root layout and each content section in a separate leaf route so every page has its own URL and metadata.
- Keep browser-safe page presentations in the shared site content module and do not fabricate external community URLs.
- Recruitment advice requires authenticated validated server functions and owner-scoped persisted recommendations; authenticated RLS prevents other members from reading advice.
- Member profile names are Roblox handles, not verified Roblox identities; Google owns sign-in and only each member can read or edit their profile.
- Public membership and recruitment pages use inline sign-in affordances with protected actions, never protected public loaders; this preserves public SSR while validating each private request.
- Store terminal AI availability/access pause state in a service-role-only table; owner repair must clear it before new user requests can resume.
