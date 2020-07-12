# Witcher 3 - RDR Horse Controls

This is mod for Witcher 3 that makes horse controls like in RDR games.

- With left stick you can still can move the horse, but it speed will be slow.
- To speed up, you need to spur the horse. The `A` button on controller and `Shift` on KB/M.
- If you will not spur the horse for some time, it will slow down.
- Hitting the spur button within 1 second window, will speed up the horse, otherwise maintain the current speed.
- Hold spur button to maintain current speed.
- To slow down use `B` on controller or `X` on KB/M.
- If you don't steer the horse, it will always follow road.

## Needed changes to `input.settings` file:

- Remove this lines from `[Horse]` and `[Horse_Replacer_Ciri]`:

```
IK_Pad_Y_TRIANGLE=(Action=VehicleAttack)
IK_Pad_B_CIRCLE=(Action=HorseJump)
IK_Pad_B_CIRCLE=(Action=HorseDismount,State=Duration,IdleTime=10000)
IK_Pad_B_CIRCLE=(Action=DebugInput)
IK_Pad_B_CIRCLE=(Action=VehicleItemActionAbort)
IK_X=(Action=Stop)
```

- Add this to the beginning of the file:

```
[Horse]
IK_Pad_B_CIRCLE=(Action=Decelerate)
IK_Pad_B_CIRCLE=(Action=Stop,State=Duration,IdleTime=0.2)
IK_Pad_Y_TRIANGLE=(Action=HorseJump)
IK_Pad_Y_TRIANGLE=(Action=HorseDismount,State=Duration,IdleTime=10000)
IK_Pad_Y_TRIANGLE=(Action=VehicleItemActionAbort)
IK_Pad_Y_TRIANGLE=(Action=DebugInput)
IK_X=(Action=Decelerate)
IK_X=(Action=Stop,State=Duration,IdleTime=0.2)

[Horse_Replacer_Ciri]
IK_Pad_B_CIRCLE=(Action=Decelerate)
IK_Pad_B_CIRCLE=(Action=Stop,State=Duration,IdleTime=0.2)
IK_Pad_Y_TRIANGLE=(Action=HorseJump)
IK_Pad_Y_TRIANGLE=(Action=HorseDismount,State=Duration,IdleTime=10000)
IK_Pad_Y_TRIANGLE=(Action=VehicleItemActionAbort)
IK_Pad_Y_TRIANGLE=(Action=DebugInput)
IK_X=(Action=Decelerate)
IK_X=(Action=Stop,State=Duration,IdleTime=0.2)
```

