---
title: Attribute Modify Transfer (Power Type)
date: 2021-10-06
---

# Attribute Modify Transfer

[Power Type](../power_types.md)

Transfers the value of an attribute modifier from a specified attribute to a specified power class that extends the [`ValueModifyingPower`](https://github.com/apace100/apoli/blob/master/src/main/java/io/github/apace100/apoli/power/ValueModifyingPower.java) super-class.

Type ID: `origins:attribute_modify_transfer`

!!! note

    The name for the power classes uses the pascal-case naming convention. One can convert it to snake-case and remove the `*Power` suffix, which will then be the string value that can be used in the `class` field of the power type.

    (e.g: `ModifyAirSpeedPower` --> `"modify_air_speed`, `ModifyBreakSpeedPower` --> `"modify_break_speed"`, etc.)

!!! note

    Refer to the [Minecraft Fandom Wiki: Attribute](https://minecraft.fandom.com/wiki/Attribute) page for a list of **vanilla** attributes that you can get the value from.


### Fields

Field | Type | Default | Description
------|------|---------|-------------
`class` | [Identifier](../data_types/identifier.md) | | The path and ID of the class to transfer the value of an attribute modifier to.
`attribute` | [Identifier](../data_types/identifier.md) | | The namespace and ID of the attribute to get the value from.
`multiplier` | [Float](../data_types/float.md) | `1.0` | Determines the multiplier for the value.
 

### Examples

```json
{
    "type": "origins:attribute_modify_transfer",
    "class": "modify_break_speed",
    "attribute": "minecraft:generic.movement_speed",
    "multiplier": 1.25
}
```

This example will transfer the value of the attribute modifier for the `minecraft:generic.movement_speed` attribute to the `modify_break_speed` (`io.github.apace100.apoli.power.ModifyBreakSpeedPower`) class, essentially giving the player mining speed boost if the player's movement speed is quite high.
