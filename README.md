# ioBroker.nexowatt-eebus

Adapter für ioBroker, der Datenpunkte für ein EEBus-/Imsys-Smart-Meter und die Steuerung durch den Energieversorger bereitstellt.

**Wichtig:** Diese Version implementiert noch **keine** echte EEBus-Kommunikation, sondern legt nur die Datenpunkte an,
damit du sie in eigenen JavaScript- oder Blockly-Skripten füllen und weiterverarbeiten kannst.

## Datenpunkte

Unter `nexowatt-eebus.0.*` werden unter anderem angelegt:

- `imsys.powerActive` (W)
- `imsys.powerReactive` (var)
- `imsys.energyImportTotal` (kWh)
- `imsys.energyExportTotal` (kWh)
- `imsys.voltageL1/L2/L3` (V)
- `imsys.currentL1/L2/L3` (A)
- `imsys.frequency` (Hz)
- `imsys.tariffCurrent` / `imsys.tariffName`
- `imsys.rawJson` (komplette Rohdaten als JSON-String)

Steuerung durch Energieversorger / EVU:

- `utility.maxPowerLimit` (max. Bezug in W)
- `utility.allowedPowerExport` (max. Einspeisung in W)
- `utility.controlMode` (0=normal, 1=reduziert, 2=aus)
- `utility.supplyState` (0=normal, 1=begrenzt, 2=getrennt)
- `utility.demandResponseLevel`
- `utility.lastCommand`
- `utility.commandTimestamp` (Unix-Zeitstempel)

## Verwendung

1. Adapter aus GitHub installieren (oder ZIP-Datei)
2. Instanz anlegen, speichern, starten
3. Unter `Objekte` die Datenpunkte `nexowatt-eebus.0.*` für deine Skripte verwenden

Später kann die echte EEBus-Anbindung im `main.js` bzw. einer eigenen `lib/eebusClient.js`
ergänzt werden.
