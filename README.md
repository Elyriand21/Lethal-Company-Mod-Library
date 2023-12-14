# Usage
```cs
using GameNetcodeStuff;
using Lethal_Library;
using MelonLoader;
using Non_Lethal_Dev_Console;

[assembly: MelonInfo(typeof(Mod), "MOD_NAME", "1.0.0", "MOD_AUTHOR")]
[assembly: MelonGame("ZeekerssRBLX", "Lethal Company")]
namespace Non_Lethal_Dev_Console
{
    public class Mod : MelonMod
    {
        static Library LC_Lib = new Library();
        PlayerControllerB Player;

        public void OnInitializeMelonMod()
        {
            if (LC_Lib.GetIsInGame())
            {
                Player = LC_Lib.GetPlayer("Player");
            }
        }

        public override void OnUpdate()
        {
            if (Player != null)
            {
                LC_Lib.SetPlayerHealth(Player, 100);
            }
        }
    }
}
```