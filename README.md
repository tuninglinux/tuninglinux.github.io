# Tuning Linux
### Tudo sobre como tunar o seu Linux

> by Felipe Facundes
###### Grupo Telegram: https://t.me/winehq_linux
###### Canal Telegram: https://t.me/s/PlayOnGit
###### Meu Telegram: @FeFacundes
###### Site: https://linuxgamers.github.io/

<br></br>

### Para deixar o seu computador muito mais rápido, eficiente, mais seguro. Aumente a performance e o FPS em JOGOS:
###### Leia. Na linha abaixo, contém 12 linhas de comando, obedeça cada comando:
```
echo -e "vm.swappiness=0" > /etc/sysctl.conf
echo -e "net.ipv4.tcp_syncookies=1" >> /etc/sysctl.conf
echo -e "net.ipv4.ip_forward=1" >> /etc/sysctl.conf
echo -e "net.ipv4.tcp_dsack=0" >> /etc/sysctl.conf
echo -e "net.ipv4.tcp_sack=0" >> /etc/sysctl.conf
echo -e "fs.file-max=100000" >> /etc/sysctl.conf
echo -e "kernel.sched_migration_cost_ns=5000000" >> /etc/sysctl.conf
echo -e "kernel.sched_autogroup_enabled=0" >> /etc/sysctl.conf
echo -e "vm.dirty_background_bytes=16777216" >> /etc/sysctl.conf
echo -e "vm.dirty_bytes=50331648" >> /etc/sysctl.conf
echo -e "kernel.pid_max=4194304" >> /etc/sysctl.conf
echo -e "vm.oom_kill_allocating_task=1" >> /etc/sysctl.conf
```

##### Em `/etc/security/limits.conf`  
###### Leia. Na linha abaixo, contém 11 linhas de comando, obedeça cada comando:
```
echo -e "hard stack unlimited" >> /etc/security/limits.conf
echo -e "nproc unlimited" >> /etc/security/limits.conf
echo -e "nofile 1048576" >> /etc/security/limits.conf
echo -e "memlock unlimited" >> /etc/security/limits.conf
echo -e "as unlimited" >> /etc/security/limits.conf
echo -e "cpu unlimited" >> /etc/security/limits.conf
echo -e "fsize unlimited" >> /etc/security/limits.conf
echo -e "memlock unlimited" >> /etc/security/limits.conf
echo -e "msgqueue unlimited" >> /etc/security/limits.conf
echo -e "locks unlimited" >> /etc/security/limits.conf
echo -e "* hard nofile 1048576" >> /etc/security/limits.conf
```
##### Inclua em `/etc/systemd/`
###### Observação, com às alterações abaixo seu computador,passará a desligar instantaneamente.
###### Leia. Na linha abaixo, contém 5 linhas de comando, obedeça cada comando:
```
cd /etc/systemd/
sudo rm system.conf
sudo rm user.conf
sudo wget https://raw.githubusercontent.com/felipefacundes/desktop/master/etc-systemd/system.conf
sudo wget https://raw.githubusercontent.com/felipefacundes/desktop/master/etc-systemd/user.conf
```

##### Crie um arquivo como o nome `.drirc` em seu diretório HOME (exemplo: `/home/joao/`)

`nano ~/.drirc`

```
<driconf>
   <device screen="0" driver="dri3">
      <application name="all">
	 <!-- Always synchronize with vertical refresh to avoid tearing -->
	 <option name="vblank_mode" value="0"/>
	 <option name="hyperz" value="true"/>
      </application>
</device>
</driconf>
```
##### Inclua `export vblank_mode=0` 
##### E inclua `export __GL_SYNC_TO_VBLANK=0` nos seguintes arquivos:
```
~/.profile
~/.zprofile
~/.bash_profile
/etc/environment
```
### Você poderá habilitar o Radv, para à sua AMDGPU RADEON, para tanto siga esse meu tutorial, super fácil:

https://amdgpu.github.io/
