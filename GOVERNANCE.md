# 🏛️ Gobernanza — mod-ale (ALE) — JainaCore Edition
**Estándar:** Staff Software Engineer L9

## 1. Directrices de Contribución y Mantenimiento
Mantenimiento de parches sobre upstream azerothcore/mod-eluna, estandarización de métodos Player/Unit.

## 2. Guardas de Ciclo de Vida y Teardown (`Hito #381`)
Las primitivas de hechizos y auras en [`UnitMethods.h`](file:///E:/JainaCore_Server/source/modules/mod-ale/src/LuaEngine/methods/UnitMethods.h) (`CastSpell`, `CastCustomSpell`, `CastSpellAoF`, `AddAura`) bloquean cualquier invocación cuando el lanzador o el objetivo tienen `IsCleanupDone()` o `IsDuringRemoveFromWorld()` activo, evitando violaciones `ASSERT(!m_cleanupDone)` durante eventos `CombatStop` / `OnPlayerLeaveCombat` ejecutados en apagados o desconexiones.
