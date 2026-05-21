## What I picked

I fixed a cart drawer quantity interaction issue.

## Why it's the highest-impact thing here

The issue appears during the shopping and checkout flow, where customers adjust quantities inside the AJAX cart drawer. After tapping the plus button, tapping minus often required a second interaction before responding, making quantity editing feel unreliable and laggy.

Because the cart drawer is directly tied to conversion and checkout confidence, I prioritized improving this interaction over broader visual changes.

## What I did

I traced the issue through the quantity selector and cart update flow. The cart UI temporarily disables pointer events while AJAX cart updates are processed, and browsers were preserving stale focus/active button states after quantity changes.

I applied a minimal fix in the quantity selector component to immediately blur tapped quantity controls after interaction, preventing stale focus states while preserving the existing cart update architecture and AJAX flow.

## What I'd do next

Next, I would continue auditing the cart drawer interactions, especially loading states and the sheath upsell flow that currently interrupts the shopping context.