# wsl2_windows_free_disk

Uma dica importantíssima para quem usa WSL2 no Windows, O WSL usa disco dinâmico,
então ele vai aumentando o tamanho do disco virtual do WSL conforme você
vai precisando de espaço. Só tem um problema, ele só aumenta o tamanho
de disco, ele não consegue diminuir sozinho (ou quase).

1. Localize o disco virtual do WSL2, algo como `C:\Users\HeliézerGonçalves\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04LTS_79rhkp1fndgsc\LocalState`,
   *este exemplo é usando UBUNTU como exemplo, em caso de outra distro, o caminho final após Packages será diferente.*
2. Abra o POWER SHELL de shutdown no WSL `wsl -- shutdown`, caso não funcione acesse esse endereço para [Shutdown WSL](https://askubuntu.com/questions/1131122/cant-restart-shutdown-ubuntu-under-wsl).
3. Digite `diskpart`, abrira um outro terminal igual cmd do windows.
4. Neste novo terminal digite `select vdisk file="C:\Users\HeliézerGonçalves\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04LTS_79rhkp1fndgsc\LocalState\ext4.vhdx"`
5. ATTACH VDISK READONLY
6. compact vdisk
7. detach vdisk


Com isso o você tera muitos gigas de volta de espaço em disco.


Fontes.

[Post Filipe Tagliatti](https://www.linkedin.com/posts/tagliatti_liberando-espa%C3%A7o-no-wsl2-activity-6866036375712522240-EK7T/?utm_source=linkedin_share&utm_medium=member_desktop_web)


