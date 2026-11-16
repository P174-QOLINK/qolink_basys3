# qolink_basys3

Integration of the QOLink link on the Digilent Basys 3: a NEORV32 SoC with the
QOLink core attached on its XBUS. The link itself lives in the board-independent
[`qolink`](https://github.com/P174-QOLINK/qolink) repo, included here as a
submodule. This repo holds only what is specific to the Basys 3.

## Clone

```
git clone --recurse-submodules https://github.com/P174-QOLINK/qolink_basys3
```

Already cloned without submodules: `git submodule update --init`.

## Layout

```
submodules/qolink   the link IP, pinned to a commit of qolink main
rtl/                top level: NEORV32 SoC + qolink on XBUS      [empty]
constraints/        XDC: pins for the link wires                 [empty]
vivado/             project script                               [empty]
sw/demo/            Ada demo application, depends on
                    submodules/qolink/sw/qolink              [empty]
```

## Status

Only the `qolink` submodule is in place. Still to come:

- a NEORV32 board submodule for the Basys 3 (there is no GAP `neorv32_basys3`
  repo yet; the GAP repos that exist are `neorv32_nexys4` and `neorv32_mercury2`)
- the top level in `rtl/`, once `qolink_xbus.vhd` exists in `qolink`
- constraints, Vivado script and the demo

The board for the final demo is not settled. If it changes, add a second
integration repo and leave `qolink` as it is.
