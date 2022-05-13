## Feature Toggles 101


### TL;DR
Feature toggles essentially are code blocks (functionality) wrapped in an if statement (condition for enabling them). 

### What are they?
Also known as “feature flags”, “feature switches”, "feature flippers" or "release toggles"; they are a way for us to turn specific functionality on and off, remotely without having to re-deploy or change the code.   Feature toggles are mainly used by engineering and DevOps teams, for a variety of use-cases. Their main goal is to mitigate various types of risk, during new feature rollouts, as much as possible.

### Feature Toggle Use Cases
- **Separating Deployment From Feature Roll-out:** Deploying code always carries technical risk. There is always the risk of new bugs or even crashing the software. Deploying features, on the other hand, introduces *user* risk. With a feature toggle, we can separate the two types of risk and handle them at different points in time.
- **Canary Releases: **Even when we split the rollout into two phases(code vs feature deployment), we can go a step further and instead of a full-on feature deployment, do a canary release. We can deploy for a minor sub-group of our users, and adjust our feature accordingly or roll it back depending on feedback.
- **Testing in Production: **Because of the complexity of modern deployment systems, Big companies like Facebook, Twitter, and others, couldn’t easily recreate their production environments for test, so in some cases, they have to run quality analysis and testing in production.
- **A/B Testing: **Ever had a different style of Facebook timeline than your friend sitting next to you? It has happened to me before. Production experiments like that, are possible with a feature toggle. We can direct half of our incoming traffic to a different version of our feature, and use pre-defined metrics to decide which of the two is better for engagement or whatever KPI is important to us.
- **Kill-switch:** If all else fails, a feature toggle gives us the ability to immediately disable or hide a feature temporarily or permanently. In cases of heavy load or a dysfunctional piece of code, we have in our arsenal a glorified kill-switch to buy us some time.

### Manual vs. Third-Party
As with anything, there is a debate of hand-coded vs pre-implemented third-party solutions. It all boils down to complexity. If we are just starting out and trying to experiment with feature toggles, it may be better to implement them ourselves. 
Otherwise, there are plenty of platforms to help us manage different types and amounts of feature toggles.

Suggestions:
- [Config Cat](https://configcat.com/)
- [LaunchDarkly](https://launchdarkly.com/)
- [Optimizely](https://www.optimizely.com/)
- [Unleash (Open-source)](https://github.com/Unleash/unleash)

### Drawbacks of using feature toggles
**Toggle debt: **each instance of a feature toggle (especially if it is created manually) introduces conditional logic that can easily get out of control.
In general, codebases need to be maintained continually, due to the danger of code rot. Clearing out unused feature toggles in a timely manner is an overhead that we need to take into consideration. It is there, that using a third-party management system can help us minimise such technical debt.

### Resources for further reading:
- [featureflags.io](https://featureflags.io/)
- [Feature Toggles (aka Feature Flags) by Pete Hodgson](https://martinfowler.com/articles/feature-toggles.html)
- [Feature flags in JavaScript](https://rollout.io/blog/started-quickly-javascript-feature-flags/)
- [FeatureBranch by Martin Fowler](https://martinfowler.com/bliki/FeatureBranch.html)

I hope this helped you learn something new. If you need another tech concept explained, please leave a comment below! 

On to the next one! Cheers!