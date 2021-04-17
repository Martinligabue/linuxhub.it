---
title: '#howto - Installare VMware Player su Fedora 30'
published: 2019-08-20
layout: post
author: Mirko B.
author_github: mirkobrombin
tags:
  - github
---
<p>Il <strong>player</strong> <strong>di</strong> <strong>VMware</strong> permette la creazione, gestione ed esecuzione di macchine virtuali. Il pacchetto offerto dall'azienda è vasto ed offre più strumenti, fra cui l'insieme Workstation/Professional.</p><p>In questa guida vediamo come installare il player su Fedora 30, la quale richiede alcuni accorgimenti come la compilazione dei moduli, al momento non supportati nella versione 5 del kernel Linux.</p><h2>Compilazione moduli</h2><p>Per prima cosa scarichiamo ed installiamo via <strong>dnf</strong>, gli strumenti necessari alla compilazione del moduli:</p><pre><code>sudo dnf install git make gcc gcc-c++ kernel-devel kernel-headers</code></pre><p>portiamoci in una locazione su cui lavorare, ad esempio nella cartella Download (Scaricati su sistemi in Italiano) del nostro utente:</p><pre><code>cd ~/Scaricati</code></pre><p>ed <a href="https://github.com/mkubecek/vmware-host-modules/releases">otteniamo</a>/scompattiamo la versione più recente della patch (la 15.1.0 nel momento in cui scrivo):</p><pre><code>wget https://github.com/mkubecek/vmware-host-modules/archive/player-15.1.0.zipunzip player-15.1.0.zip</code></pre><p>successivamente procediamo con la compilazione via <strong>make</strong>:</p><pre><code>makesudo make install</code></pre><h2>Installazione di VMware Player</h2><p>Otteniamo una copia gratuita del player dal <a href="https://my.vmware.com/en/web/vmware/free#desktop_end_user_computing/vmware_workstation_player/15_0">portale ufficiale</a> (la 15.1.0 nel momento in cui scrivo), portiamoci alla sua locazione da terminale e rendiamo il file eseguibile:</p><pre><code>chmod +x VMware-Player-*.bundle</code></pre><p>ed avviamo l'installazione:</p><pre><code>sudo ./VMware-Player-*.bundle</code></pre><p>Infine una volta terminata l'installazione (per non riavviare la macchina), carichiamo manualmente il modulo <strong>vmmon</strong>:</p><pre><code>sudo modprobe vmmon</code></pre><p>Possiamo ora avviare l'interfaccia del player dal menu applicazioni di sistema o semplicemente digitando <code>vmplayer</code>.</p><p>&nbsp;</p><p>Per dubbi e chiarimenti, utilizzate il nostro&nbsp;<a href="https://t.me/gentedilinux">gruppo Telegram</a>.</p><p><em>?Good *nix&nbsp;</em><strong><em>_Mirko</em></strong></p>