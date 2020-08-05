# Knative Integration Testing

This is Work in Progress. It is based on the
[Knative Integration Testing](https://docs.google.com/document/d/1dYtOqwVgG2O80fMlEDMobJPSoHv8xSRjbu1OO7KgLzU/edit)
design doc.

This repo will house several tests that confirm that Serving and Eventing work
together and continue to work without error during an upgrade/downgrade of the
control plane. The upgrade and downgrade could/will be controlled by the Knative
Operator in the future.

This repo will be owned by the Serving and Eventing working group.

## Phases

In order to bring the testing repo up and be useful, we should focus on
incremental phases of focused testing. This will let us get results quickly and
then incrementally add new tests and capabilities over time.

1. MVP Integration testing
   1. Tests around Eventing and Serving integrations with up/down grade testing.
      This confirms that the components can work together and not fail during
      upgrades to the control plane.
   1. Focus tests around the minimum set of components for eventing and serving
      to work. Meaning kn/eventing is installed with imc channels. kn/serving is
      installed with <TODO>
   1. Out of order installing of serving and eventing. Does it matter which
      order? Will the components recover? - Continue this type of test in all
      phases
1. Add Client
   1. Migrate or duplicate the client E2E tests to leverage kn to create serving
      and eventing components (perhaps the focus should be on different
      supported versions of serving and eventing mixing, but this could be a
      later phase).
1. Add Operators
   1. Introduce the usage of the operators for installing serving and eventing.
1. More Add-ons
   1. Test around various add-on components. Increase the testing matrix for
      serving + an ingress + eventing.
   1. Enable easy testing for additional add-ons from knative-sandbox.
