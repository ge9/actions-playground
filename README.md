
# Use actions/checkout for foreign repositories

- Do checkout with `ref` and `repository`.
- Call composite actions with a prefix like `ge9/actions-playground` and a suffix like `@main`because they won't be checked out.
- Specify `tag_name` for release.

# Example
```
    - name: checkout
    uses: actions/checkout@v4
    with:
        repository: ge9/ts-proxy
        ref: main
    - uses: ge9/actions-playground/.github/actions/tailscale@main
    with: 
        oauth-secret: ${{ secrets.TS_OAUTH_CLIENT_SECRET }}

    - name: Create Release
        uses: softprops/action-gh-release@v2
        with:
        files: ./artifacts/*
        tag_name: test
```
