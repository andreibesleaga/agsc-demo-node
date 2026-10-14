# Security policy

## Reporting a vulnerability

Report it privately, through this repository's **private vulnerability reporting**:
open the repository's **Security** tab and choose **Report a vulnerability**
(<https://github.com/andreibesleaga/agsc-demo-node/security/advisories/new>). The
report goes to the maintainer and is not public while it is being handled. A problem
in the engine that builds the node may go to the engine repository's private
reporting instead.

Please do not open a public issue for a security problem, and please do not post the
details anywhere public until a fix is released.

If private reporting is unavailable to you, use the contact page at
<https://andreibesleaga.com/contact/> and ask for a private channel; do not put the
details in the first message. The node's `security.txt` (RFC 9116) names the engine
repository's private reporting and this contact page; every one of these private
routes reaches the same maintainer.

Useful in a report: what you did, what happened, what you expected, and the exact
address of the page or file on <https://patterns.agenticsystemcore.com/>.

## What this node is

The node is static files, built by the reference engine from this repository, with no
application server, no database and no login. The interesting reports are therefore
usually about what an item, a page or a machine file publishes: an item whose text
steers an agent, a page that runs or loads something it should not, or a surface that
misleads a reader or an agent.

## Everything else

The engine's security policy applies to this repository unchanged: what to expect,
the supported versions, coordinated disclosure, and the honest limits of what the
checks prove. It is at
<https://github.com/andreibesleaga/agentic-system-core/blob/main/SECURITY.md>.
