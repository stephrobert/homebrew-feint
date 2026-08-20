# Homebrew tap for feint

[feint](https://github.com/stephrobert/feint) is a local emulator of the
Scaleway, Outscale and Exoscale clouds: one Go binary, one port, no account and
no spend. The official SDKs, CLIs and Terraform providers drive it as if it were
the real thing.

```bash
brew install stephrobert/feint/feint
feint version
```

## This formula is derived, not written

`Formula/feint.rb` is **generated** from the `checksums.txt` that the feint
release publishes and cosign signs. Do not edit it by hand.

That is the whole point of the arrangement. A tap maintained by hand goes stale
two versions later and nothing says so — so the formula here is never
transcribed. It is rendered from the digests the release already signed, which
means `brew` verifies the exact bytes that carry feint's SLSA provenance and
SBOM. Nothing is rebuilt locally.

## Updating it after a release

In a checkout of [feint](https://github.com/stephrobert/feint):

```bash
mise run release:formula > /path/to/homebrew-feint/Formula/feint.rb
```

Then commit the result here. `mise run release:tap`, in the feint repository,
derives the formula again from the latest release and **exits 2 while this tap
differs from it** — so a tap that has fallen behind is a measurement, not
something anybody has to remember to check. The same check runs on a schedule
in feint's own CI.

## Licence

The formula follows feint's licence, Apache-2.0.
