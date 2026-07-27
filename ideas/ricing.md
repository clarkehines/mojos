# Ricing

Wishlist, not commitments — shrinks as things get built, doesn't move anywhere else.

## Backbone

**Stylix** — one base16 palette + wallpaper + font declared once, propagates to every
app with a Stylix target (terminal, GTK/Qt, Hyprland, notifications). Composes with
home-manager. Anything without a Stylix target still needs hand-theming.

## Modes vs wallust — resolved

`wallust` generates a colorscheme from whatever wallpaper is set, at runtime — that's
imperative, the opposite instinct from "everything reproducible from the flake."
Resolved: modes are declarative Stylix-variable swaps (decided, see modes.md).
`wallust` stays an optional side toy outside the formal mode system if it's ever
wanted — not wired into modes.

## The one real design principle that surfaced

Cohesion beats flash. One consistent logic (font, spacing, palette *logic*, not
necessarily one literal palette) applied everywhere reads as "designed." Minimalism
and maximalism are both fine — the actual failure mode is inconsistency, not a
specific point on that spectrum. Applies directly to the retro-futurism/phosphor
aesthetic already chosen: the risk isn't picking the wrong look, it's applying it to
the terminal and forgetting about it everywhere else.

## Aesthetic direction (already established, regular/classic mode's identity)

Warm retro-futurism, aged paper, phosphor terminal look. No existing project matches
this combination — genuinely original composition, not something to find and copy.

A workshop, not a factory. Woody, not metal. Warm and inviting — the kind of space
that draws the light out of you rather than coercing you into working. Reference
points: aged paper, old NASA mission control, 1970s-80s technical instrumentation,
vintage phosphor terminals. Information-dense but not chaotic — every element earns
its place. Recovered from git history (pre-migration `raw/docs/vision/aesthetic.md`,
commit bccf2d8) since this is where the real spec lives now.

Full palette:

| Role | Hex | Feel |
|---|---|---|
| Main background | `#F2ECD8` | Aged paper — the canvas everything sits on |
| Panel background | `#E8E0C8` | Slightly darker — cards, sidebars, containers |
| Panel header / border | `#DDD5B8` | Subtle separation without hard lines |
| Primary text | `#2A1F0E` | Very dark warm brown — old ink on paper |
| Secondary text | `#5A4A2E` | Lighter warm brown — labels, metadata |
| Muted text | `#8A7A5E` | De-emphasized — timestamps, hints |
| Primary accent | `#C47820` | Amber — phosphor glow, brass instruments |
| Bright accent | `#E8960A` | Warmer amber — active states, highlights |
| Status green | `#6A9A5A` | Muted vintage green — alive, running, ok |
| Info blue | `#2A3A5A` | Dark navy — calm informational tone |
| Dark panel background | `#1C1A10` | Near-black with warm undertone — not pure black |
| Dark panel text | `#D4C89A` | Warm cream — readable, not harsh white |
| Dark panel accent | `#8AB870` | Muted phosphor green — data, status, output |
| Dark panel highlight | `#C47820` | Same amber — consistent energy color |

Typography: monospace everywhere (data, labels, readouts, code, UI chrome) — this is
a technical instrument, not a productivity app. Font candidates: Berkeley Mono,
Iosevka, JetBrains Mono. No rounded corners on text containers, hard edges suit the
look; hierarchy through weight and color, not font-size sprawl.

Layout: panel-based, not card-based — panels have defined positions and purposes,
cards float, this doesn't. Hard edges, minimal border-radius. Information-dense
grids over whitespace, trusting the warm palette to stay readable. Spatial
consistency — things live in the same place every time, reinforcing spatial memory.
Dark panels as focal points — a terminal, a data readout, a diagram lives in a dark
panel, the contrast draws the eye without shouting.

## Widget/launcher/notification options

Past what's already chosen (Hyprland, waybar, kitty, rofi-wayland, pipewire):

- Widgets: AGS/Astal — current standard for custom Hyprland shells, heavier than
  waybar, far more flexible.
- Launchers: walker, anyrun — newer, more Wayland-native than rofi-wayland.
- Notifications: mako — lightweight, has a Stylix module.
- Lock/idle: hyprlock/hypridle — Hyprland-native, tighter integration than
  swaylock/swayidle.
- catppuccin-nix — drop-in palette pack across many of the same targets Stylix covers.

None of these are decided — options to reach for if/when the current stack falls
short.
