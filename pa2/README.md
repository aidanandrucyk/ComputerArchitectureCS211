The following are the x86 assembly instructions corresponding to my bomb

```
./bomb:     file format elf32-i386


Disassembly of section .init:

080486bc <_init>:
 80486bc:	53                   	push   %ebx
 80486bd:	83 ec 08             	sub    $0x8,%esp
 80486c0:	e8 1b 02 00 00       	call   80488e0 <__x86.get_pc_thunk.bx>
 80486c5:	81 c3 3b 39 00 00    	add    $0x393b,%ebx
 80486cb:	8b 83 fc ff ff ff    	mov    -0x4(%ebx),%eax
 80486d1:	85 c0                	test   %eax,%eax
 80486d3:	74 05                	je     80486da <_init+0x1e>
 80486d5:	e8 c6 01 00 00       	call   80488a0 <.plt.got>
 80486da:	83 c4 08             	add    $0x8,%esp
 80486dd:	5b                   	pop    %ebx
 80486de:	c3                   	ret    

Disassembly of section .plt:

080486e0 <.plt>:
 80486e0:	ff 35 04 c0 04 08    	pushl  0x804c004
 80486e6:	ff 25 08 c0 04 08    	jmp    *0x804c008
 80486ec:	00 00                	add    %al,(%eax)
	...

080486f0 <read@plt>:
 80486f0:	ff 25 0c c0 04 08    	jmp    *0x804c00c
 80486f6:	68 00 00 00 00       	push   $0x0
 80486fb:	e9 e0 ff ff ff       	jmp    80486e0 <.plt>

08048700 <printf@plt>:
 8048700:	ff 25 10 c0 04 08    	jmp    *0x804c010
 8048706:	68 08 00 00 00       	push   $0x8
 804870b:	e9 d0 ff ff ff       	jmp    80486e0 <.plt>

08048710 <fflush@plt>:
 8048710:	ff 25 14 c0 04 08    	jmp    *0x804c014
 8048716:	68 10 00 00 00       	push   $0x10
 804871b:	e9 c0 ff ff ff       	jmp    80486e0 <.plt>

08048720 <memcpy@plt>:
 8048720:	ff 25 18 c0 04 08    	jmp    *0x804c018
 8048726:	68 18 00 00 00       	push   $0x18
 804872b:	e9 b0 ff ff ff       	jmp    80486e0 <.plt>

08048730 <fgets@plt>:
 8048730:	ff 25 1c c0 04 08    	jmp    *0x804c01c
 8048736:	68 20 00 00 00       	push   $0x20
 804873b:	e9 a0 ff ff ff       	jmp    80486e0 <.plt>

08048740 <signal@plt>:
 8048740:	ff 25 20 c0 04 08    	jmp    *0x804c020
 8048746:	68 28 00 00 00       	push   $0x28
 804874b:	e9 90 ff ff ff       	jmp    80486e0 <.plt>

08048750 <sleep@plt>:
 8048750:	ff 25 24 c0 04 08    	jmp    *0x804c024
 8048756:	68 30 00 00 00       	push   $0x30
 804875b:	e9 80 ff ff ff       	jmp    80486e0 <.plt>

08048760 <alarm@plt>:
 8048760:	ff 25 28 c0 04 08    	jmp    *0x804c028
 8048766:	68 38 00 00 00       	push   $0x38
 804876b:	e9 70 ff ff ff       	jmp    80486e0 <.plt>

08048770 <bcopy@plt>:
 8048770:	ff 25 2c c0 04 08    	jmp    *0x804c02c
 8048776:	68 40 00 00 00       	push   $0x40
 804877b:	e9 60 ff ff ff       	jmp    80486e0 <.plt>

08048780 <strcpy@plt>:
 8048780:	ff 25 30 c0 04 08    	jmp    *0x804c030
 8048786:	68 48 00 00 00       	push   $0x48
 804878b:	e9 50 ff ff ff       	jmp    80486e0 <.plt>

08048790 <gethostname@plt>:
 8048790:	ff 25 34 c0 04 08    	jmp    *0x804c034
 8048796:	68 50 00 00 00       	push   $0x50
 804879b:	e9 40 ff ff ff       	jmp    80486e0 <.plt>

080487a0 <getenv@plt>:
 80487a0:	ff 25 38 c0 04 08    	jmp    *0x804c038
 80487a6:	68 58 00 00 00       	push   $0x58
 80487ab:	e9 30 ff ff ff       	jmp    80486e0 <.plt>

080487b0 <puts@plt>:
 80487b0:	ff 25 3c c0 04 08    	jmp    *0x804c03c
 80487b6:	68 60 00 00 00       	push   $0x60
 80487bb:	e9 20 ff ff ff       	jmp    80486e0 <.plt>

080487c0 <exit@plt>:
 80487c0:	ff 25 40 c0 04 08    	jmp    *0x804c040
 80487c6:	68 68 00 00 00       	push   $0x68
 80487cb:	e9 10 ff ff ff       	jmp    80486e0 <.plt>

080487d0 <__libc_start_main@plt>:
 80487d0:	ff 25 44 c0 04 08    	jmp    *0x804c044
 80487d6:	68 70 00 00 00       	push   $0x70
 80487db:	e9 00 ff ff ff       	jmp    80486e0 <.plt>

080487e0 <fprintf@plt>:
 80487e0:	ff 25 48 c0 04 08    	jmp    *0x804c048
 80487e6:	68 78 00 00 00       	push   $0x78
 80487eb:	e9 f0 fe ff ff       	jmp    80486e0 <.plt>

080487f0 <write@plt>:
 80487f0:	ff 25 4c c0 04 08    	jmp    *0x804c04c
 80487f6:	68 80 00 00 00       	push   $0x80
 80487fb:	e9 e0 fe ff ff       	jmp    80486e0 <.plt>

08048800 <strcasecmp@plt>:
 8048800:	ff 25 50 c0 04 08    	jmp    *0x804c050
 8048806:	68 88 00 00 00       	push   $0x88
 804880b:	e9 d0 fe ff ff       	jmp    80486e0 <.plt>

08048810 <__isoc99_sscanf@plt>:
 8048810:	ff 25 54 c0 04 08    	jmp    *0x804c054
 8048816:	68 90 00 00 00       	push   $0x90
 804881b:	e9 c0 fe ff ff       	jmp    80486e0 <.plt>

08048820 <fopen@plt>:
 8048820:	ff 25 58 c0 04 08    	jmp    *0x804c058
 8048826:	68 98 00 00 00       	push   $0x98
 804882b:	e9 b0 fe ff ff       	jmp    80486e0 <.plt>

08048830 <__errno_location@plt>:
 8048830:	ff 25 5c c0 04 08    	jmp    *0x804c05c
 8048836:	68 a0 00 00 00       	push   $0xa0
 804883b:	e9 a0 fe ff ff       	jmp    80486e0 <.plt>

08048840 <sprintf@plt>:
 8048840:	ff 25 60 c0 04 08    	jmp    *0x804c060
 8048846:	68 a8 00 00 00       	push   $0xa8
 804884b:	e9 90 fe ff ff       	jmp    80486e0 <.plt>

08048850 <socket@plt>:
 8048850:	ff 25 64 c0 04 08    	jmp    *0x804c064
 8048856:	68 b0 00 00 00       	push   $0xb0
 804885b:	e9 80 fe ff ff       	jmp    80486e0 <.plt>

08048860 <gethostbyname@plt>:
 8048860:	ff 25 68 c0 04 08    	jmp    *0x804c068
 8048866:	68 b8 00 00 00       	push   $0xb8
 804886b:	e9 70 fe ff ff       	jmp    80486e0 <.plt>

08048870 <connect@plt>:
 8048870:	ff 25 6c c0 04 08    	jmp    *0x804c06c
 8048876:	68 c0 00 00 00       	push   $0xc0
 804887b:	e9 60 fe ff ff       	jmp    80486e0 <.plt>

08048880 <close@plt>:
 8048880:	ff 25 70 c0 04 08    	jmp    *0x804c070
 8048886:	68 c8 00 00 00       	push   $0xc8
 804888b:	e9 50 fe ff ff       	jmp    80486e0 <.plt>

08048890 <__ctype_b_loc@plt>:
 8048890:	ff 25 74 c0 04 08    	jmp    *0x804c074
 8048896:	68 d0 00 00 00       	push   $0xd0
 804889b:	e9 40 fe ff ff       	jmp    80486e0 <.plt>

Disassembly of section .plt.got:

080488a0 <.plt.got>:
 80488a0:	ff 25 fc bf 04 08    	jmp    *0x804bffc
 80488a6:	66 90                	xchg   %ax,%ax

Disassembly of section .text:

080488b0 <_start>:
 80488b0:	31 ed                	xor    %ebp,%ebp
 80488b2:	5e                   	pop    %esi
 80488b3:	89 e1                	mov    %esp,%ecx
 80488b5:	83 e4 f0             	and    $0xfffffff0,%esp
 80488b8:	50                   	push   %eax
 80488b9:	54                   	push   %esp
 80488ba:	52                   	push   %edx
 80488bb:	68 10 9f 04 08       	push   $0x8049f10
 80488c0:	68 a0 9e 04 08       	push   $0x8049ea0
 80488c5:	51                   	push   %ecx
 80488c6:	56                   	push   %esi
 80488c7:	68 ad 89 04 08       	push   $0x80489ad
 80488cc:	e8 ff fe ff ff       	call   80487d0 <__libc_start_main@plt>
 80488d1:	f4                   	hlt    
 80488d2:	66 90                	xchg   %ax,%ax
 80488d4:	66 90                	xchg   %ax,%ax
 80488d6:	66 90                	xchg   %ax,%ax
 80488d8:	66 90                	xchg   %ax,%ax
 80488da:	66 90                	xchg   %ax,%ax
 80488dc:	66 90                	xchg   %ax,%ax
 80488de:	66 90                	xchg   %ax,%ax

080488e0 <__x86.get_pc_thunk.bx>:
 80488e0:	8b 1c 24             	mov    (%esp),%ebx
 80488e3:	c3                   	ret    
 80488e4:	66 90                	xchg   %ax,%ax
 80488e6:	66 90                	xchg   %ax,%ax
 80488e8:	66 90                	xchg   %ax,%ax
 80488ea:	66 90                	xchg   %ax,%ax
 80488ec:	66 90                	xchg   %ax,%ax
 80488ee:	66 90                	xchg   %ax,%ax

080488f0 <deregister_tm_clones>:
 80488f0:	b8 23 c7 04 08       	mov    $0x804c723,%eax
 80488f5:	2d 20 c7 04 08       	sub    $0x804c720,%eax
 80488fa:	83 f8 06             	cmp    $0x6,%eax
 80488fd:	77 01                	ja     8048900 <deregister_tm_clones+0x10>
 80488ff:	c3                   	ret    
 8048900:	b8 00 00 00 00       	mov    $0x0,%eax
 8048905:	85 c0                	test   %eax,%eax
 8048907:	74 f6                	je     80488ff <deregister_tm_clones+0xf>
 8048909:	55                   	push   %ebp
 804890a:	89 e5                	mov    %esp,%ebp
 804890c:	83 ec 18             	sub    $0x18,%esp
 804890f:	c7 04 24 20 c7 04 08 	movl   $0x804c720,(%esp)
 8048916:	ff d0                	call   *%eax
 8048918:	c9                   	leave  
 8048919:	c3                   	ret    
 804891a:	8d b6 00 00 00 00    	lea    0x0(%esi),%esi

08048920 <register_tm_clones>:
 8048920:	b8 20 c7 04 08       	mov    $0x804c720,%eax
 8048925:	2d 20 c7 04 08       	sub    $0x804c720,%eax
 804892a:	c1 f8 02             	sar    $0x2,%eax
 804892d:	89 c2                	mov    %eax,%edx
 804892f:	c1 ea 1f             	shr    $0x1f,%edx
 8048932:	01 d0                	add    %edx,%eax
 8048934:	d1 f8                	sar    %eax
 8048936:	75 01                	jne    8048939 <register_tm_clones+0x19>
 8048938:	c3                   	ret    
 8048939:	ba 00 00 00 00       	mov    $0x0,%edx
 804893e:	85 d2                	test   %edx,%edx
 8048940:	74 f6                	je     8048938 <register_tm_clones+0x18>
 8048942:	55                   	push   %ebp
 8048943:	89 e5                	mov    %esp,%ebp
 8048945:	83 ec 18             	sub    $0x18,%esp
 8048948:	89 44 24 04          	mov    %eax,0x4(%esp)
 804894c:	c7 04 24 20 c7 04 08 	movl   $0x804c720,(%esp)
 8048953:	ff d2                	call   *%edx
 8048955:	c9                   	leave  
 8048956:	c3                   	ret    
 8048957:	89 f6                	mov    %esi,%esi
 8048959:	8d bc 27 00 00 00 00 	lea    0x0(%edi,%eiz,1),%edi

08048960 <__do_global_dtors_aux>:
 8048960:	80 3d 44 c7 04 08 00 	cmpb   $0x0,0x804c744
 8048967:	75 13                	jne    804897c <__do_global_dtors_aux+0x1c>
 8048969:	55                   	push   %ebp
 804896a:	89 e5                	mov    %esp,%ebp
 804896c:	83 ec 08             	sub    $0x8,%esp
 804896f:	e8 7c ff ff ff       	call   80488f0 <deregister_tm_clones>
 8048974:	c6 05 44 c7 04 08 01 	movb   $0x1,0x804c744
 804897b:	c9                   	leave  
 804897c:	f3 c3                	repz ret 
 804897e:	66 90                	xchg   %ax,%ax

08048980 <frame_dummy>:
 8048980:	a1 10 bf 04 08       	mov    0x804bf10,%eax
 8048985:	85 c0                	test   %eax,%eax
 8048987:	74 1f                	je     80489a8 <frame_dummy+0x28>
 8048989:	b8 00 00 00 00       	mov    $0x0,%eax
 804898e:	85 c0                	test   %eax,%eax
 8048990:	74 16                	je     80489a8 <frame_dummy+0x28>
 8048992:	55                   	push   %ebp
 8048993:	89 e5                	mov    %esp,%ebp
 8048995:	83 ec 18             	sub    $0x18,%esp
 8048998:	c7 04 24 10 bf 04 08 	movl   $0x804bf10,(%esp)
 804899f:	ff d0                	call   *%eax
 80489a1:	c9                   	leave  
 80489a2:	e9 79 ff ff ff       	jmp    8048920 <register_tm_clones>
 80489a7:	90                   	nop
 80489a8:	e9 73 ff ff ff       	jmp    8048920 <register_tm_clones>

080489ad <main>:
 80489ad:	55                   	push   %ebp
 80489ae:	89 e5                	mov    %esp,%ebp
 80489b0:	53                   	push   %ebx
 80489b1:	83 e4 f0             	and    $0xfffffff0,%esp
 80489b4:	83 ec 10             	sub    $0x10,%esp
 80489b7:	8b 45 08             	mov    0x8(%ebp),%eax
 80489ba:	8b 5d 0c             	mov    0xc(%ebp),%ebx
 80489bd:	83 f8 01             	cmp    $0x1,%eax
 80489c0:	75 0c                	jne    80489ce <main+0x21>
 80489c2:	a1 24 c7 04 08       	mov    0x804c724,%eax
 80489c7:	a3 4c c7 04 08       	mov    %eax,0x804c74c
 80489cc:	eb 64                	jmp    8048a32 <main+0x85>
 80489ce:	83 f8 02             	cmp    $0x2,%eax
 80489d1:	75 41                	jne    8048a14 <main+0x67>
 80489d3:	c7 44 24 04 4c 9f 04 	movl   $0x8049f4c,0x4(%esp)
 80489da:	08 
 80489db:	8b 43 04             	mov    0x4(%ebx),%eax
 80489de:	89 04 24             	mov    %eax,(%esp)
 80489e1:	e8 3a fe ff ff       	call   8048820 <fopen@plt>
 80489e6:	a3 4c c7 04 08       	mov    %eax,0x804c74c
 80489eb:	85 c0                	test   %eax,%eax
 80489ed:	75 43                	jne    8048a32 <main+0x85>
 80489ef:	8b 43 04             	mov    0x4(%ebx),%eax
 80489f2:	89 44 24 08          	mov    %eax,0x8(%esp)
 80489f6:	8b 03                	mov    (%ebx),%eax
 80489f8:	89 44 24 04          	mov    %eax,0x4(%esp)
 80489fc:	c7 04 24 4e 9f 04 08 	movl   $0x8049f4e,(%esp)
 8048a03:	e8 f8 fc ff ff       	call   8048700 <printf@plt>
 8048a08:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048a0f:	e8 ac fd ff ff       	call   80487c0 <exit@plt>
 8048a14:	8b 03                	mov    (%ebx),%eax
 8048a16:	89 44 24 04          	mov    %eax,0x4(%esp)
 8048a1a:	c7 04 24 6b 9f 04 08 	movl   $0x8049f6b,(%esp)
 8048a21:	e8 da fc ff ff       	call   8048700 <printf@plt>
 8048a26:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048a2d:	e8 8e fd ff ff       	call   80487c0 <exit@plt>
 8048a32:	e8 7f 04 00 00       	call   8048eb6 <initialize_bomb>
 8048a37:	c7 04 24 c0 9f 04 08 	movl   $0x8049fc0,(%esp)
 8048a3e:	e8 6d fd ff ff       	call   80487b0 <puts@plt>
 8048a43:	c7 04 24 fc 9f 04 08 	movl   $0x8049ffc,(%esp)
 8048a4a:	e8 61 fd ff ff       	call   80487b0 <puts@plt>
 8048a4f:	e8 20 07 00 00       	call   8049174 <read_line>
 8048a54:	89 04 24             	mov    %eax,(%esp)
 8048a57:	e8 b4 00 00 00       	call   8048b10 <phase_1>
 8048a5c:	e8 47 08 00 00       	call   80492a8 <phase_defused>
 8048a61:	c7 04 24 28 a0 04 08 	movl   $0x804a028,(%esp)
 8048a68:	e8 43 fd ff ff       	call   80487b0 <puts@plt>
 8048a6d:	e8 02 07 00 00       	call   8049174 <read_line>
 8048a72:	89 04 24             	mov    %eax,(%esp)
 8048a75:	e8 da 00 00 00       	call   8048b54 <phase_2>
 8048a7a:	e8 29 08 00 00       	call   80492a8 <phase_defused>
 8048a7f:	c7 04 24 85 9f 04 08 	movl   $0x8049f85,(%esp)
 8048a86:	e8 25 fd ff ff       	call   80487b0 <puts@plt>
 8048a8b:	e8 e4 06 00 00       	call   8049174 <read_line>
 8048a90:	89 04 24             	mov    %eax,(%esp)
 8048a93:	e8 e0 00 00 00       	call   8048b78 <phase_3>
 8048a98:	e8 0b 08 00 00       	call   80492a8 <phase_defused>
 8048a9d:	c7 04 24 a3 9f 04 08 	movl   $0x8049fa3,(%esp)
 8048aa4:	e8 07 fd ff ff       	call   80487b0 <puts@plt>
 8048aa9:	e8 c6 06 00 00       	call   8049174 <read_line>
 8048aae:	89 04 24             	mov    %eax,(%esp)
 8048ab1:	e8 13 01 00 00       	call   8048bc9 <phase_4>
 8048ab6:	e8 ed 07 00 00       	call   80492a8 <phase_defused>
 8048abb:	c7 04 24 54 a0 04 08 	movl   $0x804a054,(%esp)
 8048ac2:	e8 e9 fc ff ff       	call   80487b0 <puts@plt>
 8048ac7:	e8 a8 06 00 00       	call   8049174 <read_line>
 8048acc:	89 04 24             	mov    %eax,(%esp)
 8048acf:	e8 89 01 00 00       	call   8048c5d <phase_5>
 8048ad4:	e8 cf 07 00 00       	call   80492a8 <phase_defused>
 8048ad9:	c7 04 24 b4 9f 04 08 	movl   $0x8049fb4,(%esp)
 8048ae0:	e8 cb fc ff ff       	call   80487b0 <puts@plt>
 8048ae5:	e8 8a 06 00 00       	call   8049174 <read_line>
 8048aea:	89 04 24             	mov    %eax,(%esp)
 8048aed:	e8 df 01 00 00       	call   8048cd1 <phase_6>
 8048af2:	e8 b1 07 00 00       	call   80492a8 <phase_defused>
 8048af7:	b8 00 00 00 00       	mov    $0x0,%eax
 8048afc:	8b 5d fc             	mov    -0x4(%ebp),%ebx
 8048aff:	c9                   	leave  
 8048b00:	c3                   	ret    
 8048b01:	66 90                	xchg   %ax,%ax
 8048b03:	66 90                	xchg   %ax,%ax
 8048b05:	66 90                	xchg   %ax,%ax
 8048b07:	66 90                	xchg   %ax,%ax
 8048b09:	66 90                	xchg   %ax,%ax
 8048b0b:	66 90                	xchg   %ax,%ax
 8048b0d:	66 90                	xchg   %ax,%ax
 8048b0f:	90                   	nop

08048b10 <phase_1>:
 8048b10:	83 ec 2c             	sub    $0x2c,%esp
 8048b13:	c7 44 24 1c 00 00 00 	movl   $0x0,0x1c(%esp)
 8048b1a:	00 
 8048b1b:	8d 44 24 1c          	lea    0x1c(%esp),%eax
 8048b1f:	89 44 24 08          	mov    %eax,0x8(%esp)
 8048b23:	c7 44 24 04 e4 a2 04 	movl   $0x804a2e4,0x4(%esp)
 8048b2a:	08 
 8048b2b:	8b 44 24 30          	mov    0x30(%esp),%eax
 8048b2f:	89 04 24             	mov    %eax,(%esp)
 8048b32:	e8 d9 fc ff ff       	call   8048810 <__isoc99_sscanf@plt>
 8048b37:	83 f8 01             	cmp    $0x1,%eax
 8048b3a:	74 05                	je     8048b41 <phase_1+0x31>
 8048b3c:	e8 a4 05 00 00       	call   80490e5 <explode_bomb>
 8048b41:	81 7c 24 1c 0a 01 00 	cmpl   $0x10a,0x1c(%esp)
 8048b48:	00 
 8048b49:	74 05                	je     8048b50 <phase_1+0x40>
 8048b4b:	e8 95 05 00 00       	call   80490e5 <explode_bomb>
 8048b50:	83 c4 2c             	add    $0x2c,%esp
 8048b53:	c3                   	ret    

08048b54 <phase_2>:
 8048b54:	83 ec 1c             	sub    $0x1c,%esp
 8048b57:	c7 44 24 04 78 a0 04 	movl   $0x804a078,0x4(%esp)
 8048b5e:	08 
 8048b5f:	8b 44 24 20          	mov    0x20(%esp),%eax
 8048b63:	89 04 24             	mov    %eax,(%esp)
 8048b66:	e8 df 02 00 00       	call   8048e4a <strings_not_equal>
 8048b6b:	85 c0                	test   %eax,%eax
 8048b6d:	74 05                	je     8048b74 <phase_2+0x20>
 8048b6f:	e8 71 05 00 00       	call   80490e5 <explode_bomb>
 8048b74:	83 c4 1c             	add    $0x1c,%esp
 8048b77:	c3                   	ret    

08048b78 <phase_3>:
 8048b78:	53                   	push   %ebx
 8048b79:	83 ec 38             	sub    $0x38,%esp
 8048b7c:	8d 44 24 18          	lea    0x18(%esp),%eax
 8048b80:	89 44 24 04          	mov    %eax,0x4(%esp)
 8048b84:	8b 44 24 40          	mov    0x40(%esp),%eax
 8048b88:	89 04 24             	mov    %eax,(%esp)
 8048b8b:	e8 94 05 00 00       	call   8049124 <read_six_numbers>
 8048b90:	83 7c 24 18 00       	cmpl   $0x0,0x18(%esp)
 8048b95:	79 26                	jns    8048bbd <phase_3+0x45>
 8048b97:	e8 49 05 00 00       	call   80490e5 <explode_bomb>
 8048b9c:	eb 1f                	jmp    8048bbd <phase_3+0x45>
 8048b9e:	8d 14 5b             	lea    (%ebx,%ebx,2),%edx
 8048ba1:	8b 44 9c 14          	mov    0x14(%esp,%ebx,4),%eax
 8048ba5:	8d 04 90             	lea    (%eax,%edx,4),%eax
 8048ba8:	39 44 9c 18          	cmp    %eax,0x18(%esp,%ebx,4)
 8048bac:	74 05                	je     8048bb3 <phase_3+0x3b>
 8048bae:	e8 32 05 00 00       	call   80490e5 <explode_bomb>
 8048bb3:	83 c3 01             	add    $0x1,%ebx
 8048bb6:	83 fb 06             	cmp    $0x6,%ebx
 8048bb9:	75 e3                	jne    8048b9e <phase_3+0x26>
 8048bbb:	eb 07                	jmp    8048bc4 <phase_3+0x4c>
 8048bbd:	bb 01 00 00 00       	mov    $0x1,%ebx
 8048bc2:	eb da                	jmp    8048b9e <phase_3+0x26>
 8048bc4:	83 c4 38             	add    $0x38,%esp
 8048bc7:	5b                   	pop    %ebx
 8048bc8:	c3                   	ret    

08048bc9 <phase_4>:
 8048bc9:	83 ec 2c             	sub    $0x2c,%esp
 8048bcc:	8d 44 24 18          	lea    0x18(%esp),%eax
 8048bd0:	89 44 24 0c          	mov    %eax,0xc(%esp)
 8048bd4:	8d 44 24 1c          	lea    0x1c(%esp),%eax
 8048bd8:	89 44 24 08          	mov    %eax,0x8(%esp)
 8048bdc:	c7 44 24 04 e1 a2 04 	movl   $0x804a2e1,0x4(%esp)
 8048be3:	08 
 8048be4:	8b 44 24 30          	mov    0x30(%esp),%eax
 8048be8:	89 04 24             	mov    %eax,(%esp)
 8048beb:	e8 20 fc ff ff       	call   8048810 <__isoc99_sscanf@plt>
 8048bf0:	83 f8 01             	cmp    $0x1,%eax
 8048bf3:	7f 05                	jg     8048bfa <phase_4+0x31>
 8048bf5:	e8 eb 04 00 00       	call   80490e5 <explode_bomb>
 8048bfa:	83 7c 24 1c 07       	cmpl   $0x7,0x1c(%esp)
 8048bff:	77 3c                	ja     8048c3d <phase_4+0x74>
 8048c01:	8b 44 24 1c          	mov    0x1c(%esp),%eax
 8048c05:	ff 24 85 a0 a0 04 08 	jmp    *0x804a0a0(,%eax,4)
 8048c0c:	b8 1a 03 00 00       	mov    $0x31a,%eax
 8048c11:	eb 3b                	jmp    8048c4e <phase_4+0x85>
 8048c13:	b8 32 03 00 00       	mov    $0x332,%eax
 8048c18:	eb 34                	jmp    8048c4e <phase_4+0x85>
 8048c1a:	b8 1f 02 00 00       	mov    $0x21f,%eax
 8048c1f:	eb 2d                	jmp    8048c4e <phase_4+0x85>
 8048c21:	b8 4b 01 00 00       	mov    $0x14b,%eax
 8048c26:	eb 26                	jmp    8048c4e <phase_4+0x85>
 8048c28:	b8 89 02 00 00       	mov    $0x289,%eax
 8048c2d:	eb 1f                	jmp    8048c4e <phase_4+0x85>
 8048c2f:	b8 75 02 00 00       	mov    $0x275,%eax
 8048c34:	eb 18                	jmp    8048c4e <phase_4+0x85>
 8048c36:	b8 78 03 00 00       	mov    $0x378,%eax
 8048c3b:	eb 11                	jmp    8048c4e <phase_4+0x85>
 8048c3d:	e8 a3 04 00 00       	call   80490e5 <explode_bomb>
 8048c42:	b8 00 00 00 00       	mov    $0x0,%eax
 8048c47:	eb 05                	jmp    8048c4e <phase_4+0x85>
 8048c49:	b8 7a 03 00 00       	mov    $0x37a,%eax
 8048c4e:	3b 44 24 18          	cmp    0x18(%esp),%eax
 8048c52:	74 05                	je     8048c59 <phase_4+0x90>
 8048c54:	e8 8c 04 00 00       	call   80490e5 <explode_bomb>
 8048c59:	83 c4 2c             	add    $0x2c,%esp
 8048c5c:	c3                   	ret    

08048c5d <phase_5>:
 8048c5d:	83 ec 2c             	sub    $0x2c,%esp
 8048c60:	8d 44 24 18          	lea    0x18(%esp),%eax
 8048c64:	89 44 24 0c          	mov    %eax,0xc(%esp)
 8048c68:	8d 44 24 1c          	lea    0x1c(%esp),%eax
 8048c6c:	89 44 24 08          	mov    %eax,0x8(%esp)
 8048c70:	c7 44 24 04 e1 a2 04 	movl   $0x804a2e1,0x4(%esp)
 8048c77:	08 
 8048c78:	8b 44 24 30          	mov    0x30(%esp),%eax
 8048c7c:	89 04 24             	mov    %eax,(%esp)
 8048c7f:	e8 8c fb ff ff       	call   8048810 <__isoc99_sscanf@plt>
 8048c84:	83 f8 01             	cmp    $0x1,%eax
 8048c87:	7f 05                	jg     8048c8e <phase_5+0x31>
 8048c89:	e8 57 04 00 00       	call   80490e5 <explode_bomb>
 8048c8e:	8b 44 24 1c          	mov    0x1c(%esp),%eax
 8048c92:	83 e0 0f             	and    $0xf,%eax
 8048c95:	89 44 24 1c          	mov    %eax,0x1c(%esp)
 8048c99:	83 f8 0f             	cmp    $0xf,%eax
 8048c9c:	74 2a                	je     8048cc8 <phase_5+0x6b>
 8048c9e:	b9 00 00 00 00       	mov    $0x0,%ecx
 8048ca3:	ba 00 00 00 00       	mov    $0x0,%edx
 8048ca8:	83 c2 01             	add    $0x1,%edx
 8048cab:	8b 04 85 c0 a0 04 08 	mov    0x804a0c0(,%eax,4),%eax
 8048cb2:	01 c1                	add    %eax,%ecx
 8048cb4:	83 f8 0f             	cmp    $0xf,%eax
 8048cb7:	75 ef                	jne    8048ca8 <phase_5+0x4b>
 8048cb9:	89 44 24 1c          	mov    %eax,0x1c(%esp)
 8048cbd:	83 fa 04             	cmp    $0x4,%edx
 8048cc0:	75 06                	jne    8048cc8 <phase_5+0x6b>
 8048cc2:	3b 4c 24 18          	cmp    0x18(%esp),%ecx
 8048cc6:	74 05                	je     8048ccd <phase_5+0x70>
 8048cc8:	e8 18 04 00 00       	call   80490e5 <explode_bomb>
 8048ccd:	83 c4 2c             	add    $0x2c,%esp
 8048cd0:	c3                   	ret    

08048cd1 <phase_6>:
 8048cd1:	56                   	push   %esi
 8048cd2:	53                   	push   %ebx
 8048cd3:	83 ec 44             	sub    $0x44,%esp
 8048cd6:	8d 44 24 28          	lea    0x28(%esp),%eax
 8048cda:	89 44 24 04          	mov    %eax,0x4(%esp)
 8048cde:	8b 44 24 50          	mov    0x50(%esp),%eax
 8048ce2:	89 04 24             	mov    %eax,(%esp)
 8048ce5:	e8 3a 04 00 00       	call   8049124 <read_six_numbers>
 8048cea:	be 00 00 00 00       	mov    $0x0,%esi
 8048cef:	8b 44 b4 28          	mov    0x28(%esp,%esi,4),%eax
 8048cf3:	83 e8 01             	sub    $0x1,%eax
 8048cf6:	83 f8 05             	cmp    $0x5,%eax
 8048cf9:	76 05                	jbe    8048d00 <phase_6+0x2f>
 8048cfb:	e8 e5 03 00 00       	call   80490e5 <explode_bomb>
 8048d00:	83 c6 01             	add    $0x1,%esi
 8048d03:	83 fe 06             	cmp    $0x6,%esi
 8048d06:	75 07                	jne    8048d0f <phase_6+0x3e>
 8048d08:	bb 00 00 00 00       	mov    $0x0,%ebx
 8048d0d:	eb 38                	jmp    8048d47 <phase_6+0x76>
 8048d0f:	89 f3                	mov    %esi,%ebx
 8048d11:	8b 44 9c 28          	mov    0x28(%esp,%ebx,4),%eax
 8048d15:	39 44 b4 24          	cmp    %eax,0x24(%esp,%esi,4)
 8048d19:	75 05                	jne    8048d20 <phase_6+0x4f>
 8048d1b:	e8 c5 03 00 00       	call   80490e5 <explode_bomb>
 8048d20:	83 c3 01             	add    $0x1,%ebx
 8048d23:	83 fb 05             	cmp    $0x5,%ebx
 8048d26:	7e e9                	jle    8048d11 <phase_6+0x40>
 8048d28:	eb c5                	jmp    8048cef <phase_6+0x1e>
 8048d2a:	8b 52 08             	mov    0x8(%edx),%edx
 8048d2d:	83 c0 01             	add    $0x1,%eax
 8048d30:	39 c8                	cmp    %ecx,%eax
 8048d32:	75 f6                	jne    8048d2a <phase_6+0x59>
 8048d34:	eb 05                	jmp    8048d3b <phase_6+0x6a>
 8048d36:	ba a0 c0 04 08       	mov    $0x804c0a0,%edx
 8048d3b:	89 54 b4 10          	mov    %edx,0x10(%esp,%esi,4)
 8048d3f:	83 c3 01             	add    $0x1,%ebx
 8048d42:	83 fb 06             	cmp    $0x6,%ebx
 8048d45:	74 17                	je     8048d5e <phase_6+0x8d>
 8048d47:	89 de                	mov    %ebx,%esi
 8048d49:	8b 4c 9c 28          	mov    0x28(%esp,%ebx,4),%ecx
 8048d4d:	83 f9 01             	cmp    $0x1,%ecx
 8048d50:	7e e4                	jle    8048d36 <phase_6+0x65>
 8048d52:	b8 01 00 00 00       	mov    $0x1,%eax
 8048d57:	ba a0 c0 04 08       	mov    $0x804c0a0,%edx
 8048d5c:	eb cc                	jmp    8048d2a <phase_6+0x59>
 8048d5e:	8b 5c 24 10          	mov    0x10(%esp),%ebx
 8048d62:	8d 44 24 14          	lea    0x14(%esp),%eax
 8048d66:	8d 74 24 28          	lea    0x28(%esp),%esi
 8048d6a:	89 d9                	mov    %ebx,%ecx
 8048d6c:	8b 10                	mov    (%eax),%edx
 8048d6e:	89 51 08             	mov    %edx,0x8(%ecx)
 8048d71:	83 c0 04             	add    $0x4,%eax
 8048d74:	39 f0                	cmp    %esi,%eax
 8048d76:	74 04                	je     8048d7c <phase_6+0xab>
 8048d78:	89 d1                	mov    %edx,%ecx
 8048d7a:	eb f0                	jmp    8048d6c <phase_6+0x9b>
 8048d7c:	c7 42 08 00 00 00 00 	movl   $0x0,0x8(%edx)
 8048d83:	be 05 00 00 00       	mov    $0x5,%esi
 8048d88:	8b 43 08             	mov    0x8(%ebx),%eax
 8048d8b:	8b 00                	mov    (%eax),%eax
 8048d8d:	39 03                	cmp    %eax,(%ebx)
 8048d8f:	7e 05                	jle    8048d96 <phase_6+0xc5>
 8048d91:	e8 4f 03 00 00       	call   80490e5 <explode_bomb>
 8048d96:	8b 5b 08             	mov    0x8(%ebx),%ebx
 8048d99:	83 ee 01             	sub    $0x1,%esi
 8048d9c:	75 ea                	jne    8048d88 <phase_6+0xb7>
 8048d9e:	83 c4 44             	add    $0x44,%esp
 8048da1:	5b                   	pop    %ebx
 8048da2:	5e                   	pop    %esi
 8048da3:	c3                   	ret    
 8048da4:	66 90                	xchg   %ax,%ax
 8048da6:	66 90                	xchg   %ax,%ax
 8048da8:	66 90                	xchg   %ax,%ax
 8048daa:	66 90                	xchg   %ax,%ax
 8048dac:	66 90                	xchg   %ax,%ax
 8048dae:	66 90                	xchg   %ax,%ax

08048db0 <sig_handler>:
 8048db0:	83 ec 1c             	sub    $0x1c,%esp
 8048db3:	c7 04 24 00 a1 04 08 	movl   $0x804a100,(%esp)
 8048dba:	e8 f1 f9 ff ff       	call   80487b0 <puts@plt>
 8048dbf:	c7 04 24 03 00 00 00 	movl   $0x3,(%esp)
 8048dc6:	e8 85 f9 ff ff       	call   8048750 <sleep@plt>
 8048dcb:	c7 04 24 5d a2 04 08 	movl   $0x804a25d,(%esp)
 8048dd2:	e8 29 f9 ff ff       	call   8048700 <printf@plt>
 8048dd7:	a1 40 c7 04 08       	mov    0x804c740,%eax
 8048ddc:	89 04 24             	mov    %eax,(%esp)
 8048ddf:	e8 2c f9 ff ff       	call   8048710 <fflush@plt>
 8048de4:	c7 04 24 01 00 00 00 	movl   $0x1,(%esp)
 8048deb:	e8 60 f9 ff ff       	call   8048750 <sleep@plt>
 8048df0:	c7 04 24 65 a2 04 08 	movl   $0x804a265,(%esp)
 8048df7:	e8 b4 f9 ff ff       	call   80487b0 <puts@plt>
 8048dfc:	c7 04 24 10 00 00 00 	movl   $0x10,(%esp)
 8048e03:	e8 b8 f9 ff ff       	call   80487c0 <exit@plt>

08048e08 <invalid_phase>:
 8048e08:	83 ec 1c             	sub    $0x1c,%esp
 8048e0b:	8b 44 24 20          	mov    0x20(%esp),%eax
 8048e0f:	89 44 24 04          	mov    %eax,0x4(%esp)
 8048e13:	c7 04 24 6d a2 04 08 	movl   $0x804a26d,(%esp)
 8048e1a:	e8 e1 f8 ff ff       	call   8048700 <printf@plt>
 8048e1f:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048e26:	e8 95 f9 ff ff       	call   80487c0 <exit@plt>

08048e2b <string_length>:
 8048e2b:	8b 54 24 04          	mov    0x4(%esp),%edx
 8048e2f:	80 3a 00             	cmpb   $0x0,(%edx)
 8048e32:	74 10                	je     8048e44 <string_length+0x19>
 8048e34:	b8 00 00 00 00       	mov    $0x0,%eax
 8048e39:	83 c0 01             	add    $0x1,%eax
 8048e3c:	80 3c 02 00          	cmpb   $0x0,(%edx,%eax,1)
 8048e40:	75 f7                	jne    8048e39 <string_length+0xe>
 8048e42:	f3 c3                	repz ret 
 8048e44:	b8 00 00 00 00       	mov    $0x0,%eax
 8048e49:	c3                   	ret    

08048e4a <strings_not_equal>:
 8048e4a:	57                   	push   %edi
 8048e4b:	56                   	push   %esi
 8048e4c:	53                   	push   %ebx
 8048e4d:	83 ec 04             	sub    $0x4,%esp
 8048e50:	8b 5c 24 14          	mov    0x14(%esp),%ebx
 8048e54:	8b 74 24 18          	mov    0x18(%esp),%esi
 8048e58:	89 1c 24             	mov    %ebx,(%esp)
 8048e5b:	e8 cb ff ff ff       	call   8048e2b <string_length>
 8048e60:	89 c7                	mov    %eax,%edi
 8048e62:	89 34 24             	mov    %esi,(%esp)
 8048e65:	e8 c1 ff ff ff       	call   8048e2b <string_length>
 8048e6a:	ba 01 00 00 00       	mov    $0x1,%edx
 8048e6f:	39 c7                	cmp    %eax,%edi
 8048e71:	75 3a                	jne    8048ead <strings_not_equal+0x63>
 8048e73:	0f b6 03             	movzbl (%ebx),%eax
 8048e76:	84 c0                	test   %al,%al
 8048e78:	74 20                	je     8048e9a <strings_not_equal+0x50>
 8048e7a:	3a 06                	cmp    (%esi),%al
 8048e7c:	74 08                	je     8048e86 <strings_not_equal+0x3c>
 8048e7e:	66 90                	xchg   %ax,%ax
 8048e80:	eb 1f                	jmp    8048ea1 <strings_not_equal+0x57>
 8048e82:	3a 06                	cmp    (%esi),%al
 8048e84:	75 22                	jne    8048ea8 <strings_not_equal+0x5e>
 8048e86:	83 c3 01             	add    $0x1,%ebx
 8048e89:	83 c6 01             	add    $0x1,%esi
 8048e8c:	0f b6 03             	movzbl (%ebx),%eax
 8048e8f:	84 c0                	test   %al,%al
 8048e91:	75 ef                	jne    8048e82 <strings_not_equal+0x38>
 8048e93:	ba 00 00 00 00       	mov    $0x0,%edx
 8048e98:	eb 13                	jmp    8048ead <strings_not_equal+0x63>
 8048e9a:	ba 00 00 00 00       	mov    $0x0,%edx
 8048e9f:	eb 0c                	jmp    8048ead <strings_not_equal+0x63>
 8048ea1:	ba 01 00 00 00       	mov    $0x1,%edx
 8048ea6:	eb 05                	jmp    8048ead <strings_not_equal+0x63>
 8048ea8:	ba 01 00 00 00       	mov    $0x1,%edx
 8048ead:	89 d0                	mov    %edx,%eax
 8048eaf:	83 c4 04             	add    $0x4,%esp
 8048eb2:	5b                   	pop    %ebx
 8048eb3:	5e                   	pop    %esi
 8048eb4:	5f                   	pop    %edi
 8048eb5:	c3                   	ret    

08048eb6 <initialize_bomb>:
 8048eb6:	56                   	push   %esi
 8048eb7:	53                   	push   %ebx
 8048eb8:	81 ec 54 20 00 00    	sub    $0x2054,%esp
 8048ebe:	c7 44 24 04 b0 8d 04 	movl   $0x8048db0,0x4(%esp)
 8048ec5:	08 
 8048ec6:	c7 04 24 02 00 00 00 	movl   $0x2,(%esp)
 8048ecd:	e8 6e f8 ff ff       	call   8048740 <signal@plt>
 8048ed2:	c7 44 24 04 40 00 00 	movl   $0x40,0x4(%esp)
 8048ed9:	00 
 8048eda:	8d 84 24 10 20 00 00 	lea    0x2010(%esp),%eax
 8048ee1:	89 04 24             	mov    %eax,(%esp)
 8048ee4:	e8 a7 f8 ff ff       	call   8048790 <gethostname@plt>
 8048ee9:	85 c0                	test   %eax,%eax
 8048eeb:	75 17                	jne    8048f04 <initialize_bomb+0x4e>
 8048eed:	a1 20 c5 04 08       	mov    0x804c520,%eax
 8048ef2:	bb 00 00 00 00       	mov    $0x0,%ebx
 8048ef7:	8d b4 24 10 20 00 00 	lea    0x2010(%esp),%esi
 8048efe:	85 c0                	test   %eax,%eax
 8048f00:	75 1a                	jne    8048f1c <initialize_bomb+0x66>
 8048f02:	eb 58                	jmp    8048f5c <initialize_bomb+0xa6>
 8048f04:	c7 04 24 38 a1 04 08 	movl   $0x804a138,(%esp)
 8048f0b:	e8 a0 f8 ff ff       	call   80487b0 <puts@plt>
 8048f10:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048f17:	e8 a4 f8 ff ff       	call   80487c0 <exit@plt>
 8048f1c:	89 74 24 04          	mov    %esi,0x4(%esp)
 8048f20:	89 04 24             	mov    %eax,(%esp)
 8048f23:	e8 d8 f8 ff ff       	call   8048800 <strcasecmp@plt>
 8048f28:	85 c0                	test   %eax,%eax
 8048f2a:	74 48                	je     8048f74 <initialize_bomb+0xbe>
 8048f2c:	83 c3 01             	add    $0x1,%ebx
 8048f2f:	8b 04 9d 20 c5 04 08 	mov    0x804c520(,%ebx,4),%eax
 8048f36:	85 c0                	test   %eax,%eax
 8048f38:	75 e2                	jne    8048f1c <initialize_bomb+0x66>
 8048f3a:	eb 20                	jmp    8048f5c <initialize_bomb+0xa6>
 8048f3c:	8d 44 24 10          	lea    0x10(%esp),%eax
 8048f40:	89 44 24 04          	mov    %eax,0x4(%esp)
 8048f44:	c7 04 24 7e a2 04 08 	movl   $0x804a27e,(%esp)
 8048f4b:	e8 b0 f7 ff ff       	call   8048700 <printf@plt>
 8048f50:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048f57:	e8 64 f8 ff ff       	call   80487c0 <exit@plt>
 8048f5c:	c7 04 24 70 a1 04 08 	movl   $0x804a170,(%esp)
 8048f63:	e8 48 f8 ff ff       	call   80487b0 <puts@plt>
 8048f68:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 8048f6f:	e8 4c f8 ff ff       	call   80487c0 <exit@plt>
 8048f74:	8d 44 24 10          	lea    0x10(%esp),%eax
 8048f78:	89 04 24             	mov    %eax,(%esp)
 8048f7b:	e8 ba 0c 00 00       	call   8049c3a <init_driver>
 8048f80:	85 c0                	test   %eax,%eax
 8048f82:	78 b8                	js     8048f3c <initialize_bomb+0x86>
 8048f84:	81 c4 54 20 00 00    	add    $0x2054,%esp
 8048f8a:	5b                   	pop    %ebx
 8048f8b:	5e                   	pop    %esi
 8048f8c:	c3                   	ret    

08048f8d <initialize_bomb_solve>:
 8048f8d:	f3 c3                	repz ret 

08048f8f <blank_line>:
 8048f8f:	56                   	push   %esi
 8048f90:	53                   	push   %ebx
 8048f91:	83 ec 04             	sub    $0x4,%esp
 8048f94:	8b 5c 24 10          	mov    0x10(%esp),%ebx
 8048f98:	eb 16                	jmp    8048fb0 <blank_line+0x21>
 8048f9a:	e8 f1 f8 ff ff       	call   8048890 <__ctype_b_loc@plt>
 8048f9f:	83 c3 01             	add    $0x1,%ebx
 8048fa2:	89 f2                	mov    %esi,%edx
 8048fa4:	0f be f2             	movsbl %dl,%esi
 8048fa7:	8b 00                	mov    (%eax),%eax
 8048fa9:	f6 44 70 01 20       	testb  $0x20,0x1(%eax,%esi,2)
 8048fae:	74 10                	je     8048fc0 <blank_line+0x31>
 8048fb0:	0f b6 33             	movzbl (%ebx),%esi
 8048fb3:	89 f0                	mov    %esi,%eax
 8048fb5:	84 c0                	test   %al,%al
 8048fb7:	75 e1                	jne    8048f9a <blank_line+0xb>
 8048fb9:	b8 01 00 00 00       	mov    $0x1,%eax
 8048fbe:	eb 05                	jmp    8048fc5 <blank_line+0x36>
 8048fc0:	b8 00 00 00 00       	mov    $0x0,%eax
 8048fc5:	83 c4 04             	add    $0x4,%esp
 8048fc8:	5b                   	pop    %ebx
 8048fc9:	5e                   	pop    %esi
 8048fca:	c3                   	ret    

08048fcb <skip>:
 8048fcb:	53                   	push   %ebx
 8048fcc:	83 ec 18             	sub    $0x18,%esp
 8048fcf:	a1 4c c7 04 08       	mov    0x804c74c,%eax
 8048fd4:	89 44 24 08          	mov    %eax,0x8(%esp)
 8048fd8:	c7 44 24 04 50 00 00 	movl   $0x50,0x4(%esp)
 8048fdf:	00 
 8048fe0:	a1 48 c7 04 08       	mov    0x804c748,%eax
 8048fe5:	8d 04 80             	lea    (%eax,%eax,4),%eax
 8048fe8:	c1 e0 04             	shl    $0x4,%eax
 8048feb:	05 60 c7 04 08       	add    $0x804c760,%eax
 8048ff0:	89 04 24             	mov    %eax,(%esp)
 8048ff3:	e8 38 f7 ff ff       	call   8048730 <fgets@plt>
 8048ff8:	89 c3                	mov    %eax,%ebx
 8048ffa:	85 c0                	test   %eax,%eax
 8048ffc:	74 0c                	je     804900a <skip+0x3f>
 8048ffe:	89 04 24             	mov    %eax,(%esp)
 8049001:	e8 89 ff ff ff       	call   8048f8f <blank_line>
 8049006:	85 c0                	test   %eax,%eax
 8049008:	75 c5                	jne    8048fcf <skip+0x4>
 804900a:	89 d8                	mov    %ebx,%eax
 804900c:	83 c4 18             	add    $0x18,%esp
 804900f:	5b                   	pop    %ebx
 8049010:	c3                   	ret    

08049011 <send_msg>:
 8049011:	57                   	push   %edi
 8049012:	53                   	push   %ebx
 8049013:	81 ec 24 40 00 00    	sub    $0x4024,%esp
 8049019:	8b 15 48 c7 04 08    	mov    0x804c748,%edx
 804901f:	8d 5c 92 fb          	lea    -0x5(%edx,%edx,4),%ebx
 8049023:	c1 e3 04             	shl    $0x4,%ebx
 8049026:	81 c3 60 c7 04 08    	add    $0x804c760,%ebx
 804902c:	89 df                	mov    %ebx,%edi
 804902e:	b8 00 00 00 00       	mov    $0x0,%eax
 8049033:	b9 ff ff ff ff       	mov    $0xffffffff,%ecx
 8049038:	f2 ae                	repnz scas %es:(%edi),%al
 804903a:	f7 d1                	not    %ecx
 804903c:	83 c1 63             	add    $0x63,%ecx
 804903f:	81 f9 00 20 00 00    	cmp    $0x2000,%ecx
 8049045:	76 18                	jbe    804905f <send_msg+0x4e>
 8049047:	c7 04 24 a8 a1 04 08 	movl   $0x804a1a8,(%esp)
 804904e:	e8 ad f6 ff ff       	call   8048700 <printf@plt>
 8049053:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 804905a:	e8 61 f7 ff ff       	call   80487c0 <exit@plt>
 804905f:	83 bc 24 30 40 00 00 	cmpl   $0x0,0x4030(%esp)
 8049066:	00 
 8049067:	b8 98 a2 04 08       	mov    $0x804a298,%eax
 804906c:	b9 a0 a2 04 08       	mov    $0x804a2a0,%ecx
 8049071:	0f 44 c1             	cmove  %ecx,%eax
 8049074:	89 5c 24 14          	mov    %ebx,0x14(%esp)
 8049078:	89 54 24 10          	mov    %edx,0x10(%esp)
 804907c:	89 44 24 0c          	mov    %eax,0xc(%esp)
 8049080:	a1 00 c5 04 08       	mov    0x804c500,%eax
 8049085:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049089:	c7 44 24 04 a9 a2 04 	movl   $0x804a2a9,0x4(%esp)
 8049090:	08 
 8049091:	8d 9c 24 20 20 00 00 	lea    0x2020(%esp),%ebx
 8049098:	89 1c 24             	mov    %ebx,(%esp)
 804909b:	e8 a0 f7 ff ff       	call   8048840 <sprintf@plt>
 80490a0:	8d 44 24 20          	lea    0x20(%esp),%eax
 80490a4:	89 44 24 0c          	mov    %eax,0xc(%esp)
 80490a8:	c7 44 24 08 00 00 00 	movl   $0x0,0x8(%esp)
 80490af:	00 
 80490b0:	89 5c 24 04          	mov    %ebx,0x4(%esp)
 80490b4:	c7 04 24 00 c1 04 08 	movl   $0x804c100,(%esp)
 80490bb:	e8 52 0d 00 00       	call   8049e12 <driver_post>
 80490c0:	85 c0                	test   %eax,%eax
 80490c2:	79 18                	jns    80490dc <send_msg+0xcb>
 80490c4:	8d 44 24 20          	lea    0x20(%esp),%eax
 80490c8:	89 04 24             	mov    %eax,(%esp)
 80490cb:	e8 e0 f6 ff ff       	call   80487b0 <puts@plt>
 80490d0:	c7 04 24 00 00 00 00 	movl   $0x0,(%esp)
 80490d7:	e8 e4 f6 ff ff       	call   80487c0 <exit@plt>
 80490dc:	81 c4 24 40 00 00    	add    $0x4024,%esp
 80490e2:	5b                   	pop    %ebx
 80490e3:	5f                   	pop    %edi
 80490e4:	c3                   	ret    

080490e5 <explode_bomb>:
 80490e5:	83 ec 1c             	sub    $0x1c,%esp
 80490e8:	c7 04 24 b5 a2 04 08 	movl   $0x804a2b5,(%esp)
 80490ef:	e8 bc f6 ff ff       	call   80487b0 <puts@plt>
 80490f4:	c7 04 24 be a2 04 08 	movl   $0x804a2be,(%esp)
 80490fb:	e8 b0 f6 ff ff       	call   80487b0 <puts@plt>
 8049100:	c7 04 24 00 00 00 00 	movl   $0x0,(%esp)
 8049107:	e8 05 ff ff ff       	call   8049011 <send_msg>
 804910c:	c7 04 24 cc a1 04 08 	movl   $0x804a1cc,(%esp)
 8049113:	e8 98 f6 ff ff       	call   80487b0 <puts@plt>
 8049118:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 804911f:	e8 9c f6 ff ff       	call   80487c0 <exit@plt>

08049124 <read_six_numbers>:
 8049124:	83 ec 2c             	sub    $0x2c,%esp
 8049127:	8b 44 24 34          	mov    0x34(%esp),%eax
 804912b:	8d 50 14             	lea    0x14(%eax),%edx
 804912e:	89 54 24 1c          	mov    %edx,0x1c(%esp)
 8049132:	8d 50 10             	lea    0x10(%eax),%edx
 8049135:	89 54 24 18          	mov    %edx,0x18(%esp)
 8049139:	8d 50 0c             	lea    0xc(%eax),%edx
 804913c:	89 54 24 14          	mov    %edx,0x14(%esp)
 8049140:	8d 50 08             	lea    0x8(%eax),%edx
 8049143:	89 54 24 10          	mov    %edx,0x10(%esp)
 8049147:	8d 50 04             	lea    0x4(%eax),%edx
 804914a:	89 54 24 0c          	mov    %edx,0xc(%esp)
 804914e:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049152:	c7 44 24 04 d5 a2 04 	movl   $0x804a2d5,0x4(%esp)
 8049159:	08 
 804915a:	8b 44 24 30          	mov    0x30(%esp),%eax
 804915e:	89 04 24             	mov    %eax,(%esp)
 8049161:	e8 aa f6 ff ff       	call   8048810 <__isoc99_sscanf@plt>
 8049166:	83 f8 05             	cmp    $0x5,%eax
 8049169:	7f 05                	jg     8049170 <read_six_numbers+0x4c>
 804916b:	e8 75 ff ff ff       	call   80490e5 <explode_bomb>
 8049170:	83 c4 2c             	add    $0x2c,%esp
 8049173:	c3                   	ret    

08049174 <read_line>:
 8049174:	57                   	push   %edi
 8049175:	56                   	push   %esi
 8049176:	53                   	push   %ebx
 8049177:	83 ec 10             	sub    $0x10,%esp
 804917a:	e8 4c fe ff ff       	call   8048fcb <skip>
 804917f:	85 c0                	test   %eax,%eax
 8049181:	75 6c                	jne    80491ef <read_line+0x7b>
 8049183:	a1 24 c7 04 08       	mov    0x804c724,%eax
 8049188:	39 05 4c c7 04 08    	cmp    %eax,0x804c74c
 804918e:	75 18                	jne    80491a8 <read_line+0x34>
 8049190:	c7 04 24 e7 a2 04 08 	movl   $0x804a2e7,(%esp)
 8049197:	e8 14 f6 ff ff       	call   80487b0 <puts@plt>
 804919c:	c7 04 24 08 00 00 00 	movl   $0x8,(%esp)
 80491a3:	e8 18 f6 ff ff       	call   80487c0 <exit@plt>
 80491a8:	c7 04 24 05 a3 04 08 	movl   $0x804a305,(%esp)
 80491af:	e8 ec f5 ff ff       	call   80487a0 <getenv@plt>
 80491b4:	85 c0                	test   %eax,%eax
 80491b6:	74 0c                	je     80491c4 <read_line+0x50>
 80491b8:	c7 04 24 00 00 00 00 	movl   $0x0,(%esp)
 80491bf:	e8 fc f5 ff ff       	call   80487c0 <exit@plt>
 80491c4:	a1 24 c7 04 08       	mov    0x804c724,%eax
 80491c9:	a3 4c c7 04 08       	mov    %eax,0x804c74c
 80491ce:	e8 f8 fd ff ff       	call   8048fcb <skip>
 80491d3:	85 c0                	test   %eax,%eax
 80491d5:	75 18                	jne    80491ef <read_line+0x7b>
 80491d7:	c7 04 24 e7 a2 04 08 	movl   $0x804a2e7,(%esp)
 80491de:	e8 cd f5 ff ff       	call   80487b0 <puts@plt>
 80491e3:	c7 04 24 00 00 00 00 	movl   $0x0,(%esp)
 80491ea:	e8 d1 f5 ff ff       	call   80487c0 <exit@plt>
 80491ef:	8b 15 48 c7 04 08    	mov    0x804c748,%edx
 80491f5:	8d 1c 92             	lea    (%edx,%edx,4),%ebx
 80491f8:	c1 e3 04             	shl    $0x4,%ebx
 80491fb:	81 c3 60 c7 04 08    	add    $0x804c760,%ebx
 8049201:	89 df                	mov    %ebx,%edi
 8049203:	b8 00 00 00 00       	mov    $0x0,%eax
 8049208:	b9 ff ff ff ff       	mov    $0xffffffff,%ecx
 804920d:	f2 ae                	repnz scas %es:(%edi),%al
 804920f:	f7 d1                	not    %ecx
 8049211:	83 e9 01             	sub    $0x1,%ecx
 8049214:	83 f9 4e             	cmp    $0x4e,%ecx
 8049217:	7e 6f                	jle    8049288 <read_line+0x114>
 8049219:	c7 04 24 10 a3 04 08 	movl   $0x804a310,(%esp)
 8049220:	e8 8b f5 ff ff       	call   80487b0 <puts@plt>
 8049225:	a1 48 c7 04 08       	mov    0x804c748,%eax
 804922a:	8d 50 01             	lea    0x1(%eax),%edx
 804922d:	89 15 48 c7 04 08    	mov    %edx,0x804c748
 8049233:	6b c0 50             	imul   $0x50,%eax,%eax
 8049236:	8d 90 60 c7 04 08    	lea    0x804c760(%eax),%edx
 804923c:	89 d7                	mov    %edx,%edi
 804923e:	be 2b a3 04 08       	mov    $0x804a32b,%esi
 8049243:	b8 10 00 00 00       	mov    $0x10,%eax
 8049248:	f6 c2 01             	test   $0x1,%dl
 804924b:	74 03                	je     8049250 <read_line+0xdc>
 804924d:	a4                   	movsb  %ds:(%esi),%es:(%edi)
 804924e:	b0 0f                	mov    $0xf,%al
 8049250:	f7 c7 02 00 00 00    	test   $0x2,%edi
 8049256:	74 05                	je     804925d <read_line+0xe9>
 8049258:	66 a5                	movsw  %ds:(%esi),%es:(%edi)
 804925a:	83 e8 02             	sub    $0x2,%eax
 804925d:	89 c1                	mov    %eax,%ecx
 804925f:	c1 e9 02             	shr    $0x2,%ecx
 8049262:	f3 a5                	rep movsl %ds:(%esi),%es:(%edi)
 8049264:	ba 00 00 00 00       	mov    $0x0,%edx
 8049269:	a8 02                	test   $0x2,%al
 804926b:	74 0b                	je     8049278 <read_line+0x104>
 804926d:	0f b7 16             	movzwl (%esi),%edx
 8049270:	66 89 17             	mov    %dx,(%edi)
 8049273:	ba 02 00 00 00       	mov    $0x2,%edx
 8049278:	a8 01                	test   $0x1,%al
 804927a:	74 07                	je     8049283 <read_line+0x10f>
 804927c:	0f b6 04 16          	movzbl (%esi,%edx,1),%eax
 8049280:	88 04 17             	mov    %al,(%edi,%edx,1)
 8049283:	e8 5d fe ff ff       	call   80490e5 <explode_bomb>
 8049288:	8d 04 92             	lea    (%edx,%edx,4),%eax
 804928b:	c1 e0 04             	shl    $0x4,%eax
 804928e:	c6 84 01 5f c7 04 08 	movb   $0x0,0x804c75f(%ecx,%eax,1)
 8049295:	00 
 8049296:	83 c2 01             	add    $0x1,%edx
 8049299:	89 15 48 c7 04 08    	mov    %edx,0x804c748
 804929f:	89 d8                	mov    %ebx,%eax
 80492a1:	83 c4 10             	add    $0x10,%esp
 80492a4:	5b                   	pop    %ebx
 80492a5:	5e                   	pop    %esi
 80492a6:	5f                   	pop    %edi
 80492a7:	c3                   	ret    

080492a8 <phase_defused>:
 80492a8:	83 ec 1c             	sub    $0x1c,%esp
 80492ab:	c7 04 24 01 00 00 00 	movl   $0x1,(%esp)
 80492b2:	e8 5a fd ff ff       	call   8049011 <send_msg>
 80492b7:	83 3d 48 c7 04 08 06 	cmpl   $0x6,0x804c748
 80492be:	75 18                	jne    80492d8 <phase_defused+0x30>
 80492c0:	c7 04 24 f0 a1 04 08 	movl   $0x804a1f0,(%esp)
 80492c7:	e8 e4 f4 ff ff       	call   80487b0 <puts@plt>
 80492cc:	c7 04 24 1c a2 04 08 	movl   $0x804a21c,(%esp)
 80492d3:	e8 d8 f4 ff ff       	call   80487b0 <puts@plt>
 80492d8:	83 c4 1c             	add    $0x1c,%esp
 80492db:	c3                   	ret    
 80492dc:	66 90                	xchg   %ax,%ax
 80492de:	66 90                	xchg   %ax,%ax

080492e0 <sigalrm_handler>:
 80492e0:	83 ec 1c             	sub    $0x1c,%esp
 80492e3:	c7 44 24 08 00 00 00 	movl   $0x0,0x8(%esp)
 80492ea:	00 
 80492eb:	c7 44 24 04 40 a7 04 	movl   $0x804a740,0x4(%esp)
 80492f2:	08 
 80492f3:	a1 20 c7 04 08       	mov    0x804c720,%eax
 80492f8:	89 04 24             	mov    %eax,(%esp)
 80492fb:	e8 e0 f4 ff ff       	call   80487e0 <fprintf@plt>
 8049300:	c7 04 24 01 00 00 00 	movl   $0x1,(%esp)
 8049307:	e8 b4 f4 ff ff       	call   80487c0 <exit@plt>

0804930c <rio_readlineb>:
 804930c:	55                   	push   %ebp
 804930d:	57                   	push   %edi
 804930e:	56                   	push   %esi
 804930f:	53                   	push   %ebx
 8049310:	83 ec 3c             	sub    $0x3c,%esp
 8049313:	89 d5                	mov    %edx,%ebp
 8049315:	83 f9 01             	cmp    $0x1,%ecx
 8049318:	0f 86 c6 00 00 00    	jbe    80493e4 <rio_readlineb+0xd8>
 804931e:	89 c3                	mov    %eax,%ebx
 8049320:	89 4c 24 1c          	mov    %ecx,0x1c(%esp)
 8049324:	c7 44 24 10 01 00 00 	movl   $0x1,0x10(%esp)
 804932b:	00 
 804932c:	8d 78 0c             	lea    0xc(%eax),%edi
 804932f:	eb 34                	jmp    8049365 <rio_readlineb+0x59>
 8049331:	c7 44 24 08 00 20 00 	movl   $0x2000,0x8(%esp)
 8049338:	00 
 8049339:	89 7c 24 04          	mov    %edi,0x4(%esp)
 804933d:	8b 03                	mov    (%ebx),%eax
 804933f:	89 04 24             	mov    %eax,(%esp)
 8049342:	e8 a9 f3 ff ff       	call   80486f0 <read@plt>
 8049347:	89 43 04             	mov    %eax,0x4(%ebx)
 804934a:	85 c0                	test   %eax,%eax
 804934c:	79 0f                	jns    804935d <rio_readlineb+0x51>
 804934e:	e8 dd f4 ff ff       	call   8048830 <__errno_location@plt>
 8049353:	83 38 04             	cmpl   $0x4,(%eax)
 8049356:	74 0d                	je     8049365 <rio_readlineb+0x59>
 8049358:	e9 99 00 00 00       	jmp    80493f6 <rio_readlineb+0xea>
 804935d:	85 c0                	test   %eax,%eax
 804935f:	90                   	nop
 8049360:	74 66                	je     80493c8 <rio_readlineb+0xbc>
 8049362:	89 7b 08             	mov    %edi,0x8(%ebx)
 8049365:	8b 73 04             	mov    0x4(%ebx),%esi
 8049368:	85 f6                	test   %esi,%esi
 804936a:	7e c5                	jle    8049331 <rio_readlineb+0x25>
 804936c:	85 f6                	test   %esi,%esi
 804936e:	0f 95 c0             	setne  %al
 8049371:	0f b6 c0             	movzbl %al,%eax
 8049374:	89 44 24 14          	mov    %eax,0x14(%esp)
 8049378:	8b 4b 08             	mov    0x8(%ebx),%ecx
 804937b:	89 44 24 08          	mov    %eax,0x8(%esp)
 804937f:	89 4c 24 18          	mov    %ecx,0x18(%esp)
 8049383:	89 4c 24 04          	mov    %ecx,0x4(%esp)
 8049387:	8d 54 24 2f          	lea    0x2f(%esp),%edx
 804938b:	89 14 24             	mov    %edx,(%esp)
 804938e:	e8 8d f3 ff ff       	call   8048720 <memcpy@plt>
 8049393:	8b 4c 24 18          	mov    0x18(%esp),%ecx
 8049397:	8b 54 24 14          	mov    0x14(%esp),%edx
 804939b:	01 d1                	add    %edx,%ecx
 804939d:	89 4b 08             	mov    %ecx,0x8(%ebx)
 80493a0:	29 d6                	sub    %edx,%esi
 80493a2:	89 73 04             	mov    %esi,0x4(%ebx)
 80493a5:	83 fa 01             	cmp    $0x1,%edx
 80493a8:	75 11                	jne    80493bb <rio_readlineb+0xaf>
 80493aa:	83 c5 01             	add    $0x1,%ebp
 80493ad:	0f b6 44 24 2f       	movzbl 0x2f(%esp),%eax
 80493b2:	88 45 ff             	mov    %al,-0x1(%ebp)
 80493b5:	3c 0a                	cmp    $0xa,%al
 80493b7:	75 1a                	jne    80493d3 <rio_readlineb+0xc7>
 80493b9:	eb 31                	jmp    80493ec <rio_readlineb+0xe0>
 80493bb:	83 7c 24 14 00       	cmpl   $0x0,0x14(%esp)
 80493c0:	75 3b                	jne    80493fd <rio_readlineb+0xf1>
 80493c2:	8b 44 24 10          	mov    0x10(%esp),%eax
 80493c6:	eb 04                	jmp    80493cc <rio_readlineb+0xc0>
 80493c8:	8b 44 24 10          	mov    0x10(%esp),%eax
 80493cc:	83 f8 01             	cmp    $0x1,%eax
 80493cf:	75 1b                	jne    80493ec <rio_readlineb+0xe0>
 80493d1:	eb 31                	jmp    8049404 <rio_readlineb+0xf8>
 80493d3:	83 44 24 10 01       	addl   $0x1,0x10(%esp)
 80493d8:	8b 44 24 1c          	mov    0x1c(%esp),%eax
 80493dc:	39 44 24 10          	cmp    %eax,0x10(%esp)
 80493e0:	74 0a                	je     80493ec <rio_readlineb+0xe0>
 80493e2:	eb 81                	jmp    8049365 <rio_readlineb+0x59>
 80493e4:	c7 44 24 10 01 00 00 	movl   $0x1,0x10(%esp)
 80493eb:	00 
 80493ec:	c6 45 00 00          	movb   $0x0,0x0(%ebp)
 80493f0:	8b 44 24 10          	mov    0x10(%esp),%eax
 80493f4:	eb 13                	jmp    8049409 <rio_readlineb+0xfd>
 80493f6:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 80493fb:	eb 0c                	jmp    8049409 <rio_readlineb+0xfd>
 80493fd:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049402:	eb 05                	jmp    8049409 <rio_readlineb+0xfd>
 8049404:	b8 00 00 00 00       	mov    $0x0,%eax
 8049409:	83 c4 3c             	add    $0x3c,%esp
 804940c:	5b                   	pop    %ebx
 804940d:	5e                   	pop    %esi
 804940e:	5f                   	pop    %edi
 804940f:	5d                   	pop    %ebp
 8049410:	c3                   	ret    

08049411 <submitr>:
 8049411:	55                   	push   %ebp
 8049412:	57                   	push   %edi
 8049413:	56                   	push   %esi
 8049414:	53                   	push   %ebx
 8049415:	81 ec 5c a0 00 00    	sub    $0xa05c,%esp
 804941b:	8b 9c 24 84 a0 00 00 	mov    0xa084(%esp),%ebx
 8049422:	c7 84 24 30 20 00 00 	movl   $0x0,0x2030(%esp)
 8049429:	00 00 00 00 
 804942d:	c7 44 24 08 00 00 00 	movl   $0x0,0x8(%esp)
 8049434:	00 
 8049435:	c7 44 24 04 01 00 00 	movl   $0x1,0x4(%esp)
 804943c:	00 
 804943d:	c7 04 24 02 00 00 00 	movl   $0x2,(%esp)
 8049444:	e8 07 f4 ff ff       	call   8048850 <socket@plt>
 8049449:	89 c5                	mov    %eax,%ebp
 804944b:	85 c0                	test   %eax,%eax
 804944d:	79 55                	jns    80494a4 <submitr+0x93>
 804944f:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049456:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 804945c:	c7 40 04 72 3a 20 43 	movl   $0x43203a72,0x4(%eax)
 8049463:	c7 40 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%eax)
 804946a:	c7 40 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%eax)
 8049471:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 8049478:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 804947f:	c7 40 18 63 72 65 61 	movl   $0x61657263,0x18(%eax)
 8049486:	c7 40 1c 74 65 20 73 	movl   $0x73206574,0x1c(%eax)
 804948d:	c7 40 20 6f 63 6b 65 	movl   $0x656b636f,0x20(%eax)
 8049494:	66 c7 40 24 74 00    	movw   $0x74,0x24(%eax)
 804949a:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 804949f:	e9 54 07 00 00       	jmp    8049bf8 <submitr+0x7e7>
 80494a4:	8b 84 24 70 a0 00 00 	mov    0xa070(%esp),%eax
 80494ab:	89 04 24             	mov    %eax,(%esp)
 80494ae:	e8 ad f3 ff ff       	call   8048860 <gethostbyname@plt>
 80494b3:	85 c0                	test   %eax,%eax
 80494b5:	75 6f                	jne    8049526 <submitr+0x115>
 80494b7:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 80494be:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 80494c4:	c7 40 04 72 3a 20 44 	movl   $0x44203a72,0x4(%eax)
 80494cb:	c7 40 08 4e 53 20 69 	movl   $0x6920534e,0x8(%eax)
 80494d2:	c7 40 0c 73 20 75 6e 	movl   $0x6e752073,0xc(%eax)
 80494d9:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 80494e0:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 80494e7:	c7 40 18 72 65 73 6f 	movl   $0x6f736572,0x18(%eax)
 80494ee:	c7 40 1c 6c 76 65 20 	movl   $0x2065766c,0x1c(%eax)
 80494f5:	c7 40 20 73 65 72 76 	movl   $0x76726573,0x20(%eax)
 80494fc:	c7 40 24 65 72 20 61 	movl   $0x61207265,0x24(%eax)
 8049503:	c7 40 28 64 64 72 65 	movl   $0x65726464,0x28(%eax)
 804950a:	66 c7 40 2c 73 73    	movw   $0x7373,0x2c(%eax)
 8049510:	c6 40 2e 00          	movb   $0x0,0x2e(%eax)
 8049514:	89 2c 24             	mov    %ebp,(%esp)
 8049517:	e8 64 f3 ff ff       	call   8048880 <close@plt>
 804951c:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049521:	e9 d2 06 00 00       	jmp    8049bf8 <submitr+0x7e7>
 8049526:	8d b4 24 40 a0 00 00 	lea    0xa040(%esp),%esi
 804952d:	c7 84 24 40 a0 00 00 	movl   $0x0,0xa040(%esp)
 8049534:	00 00 00 00 
 8049538:	c7 84 24 44 a0 00 00 	movl   $0x0,0xa044(%esp)
 804953f:	00 00 00 00 
 8049543:	c7 84 24 48 a0 00 00 	movl   $0x0,0xa048(%esp)
 804954a:	00 00 00 00 
 804954e:	c7 84 24 4c a0 00 00 	movl   $0x0,0xa04c(%esp)
 8049555:	00 00 00 00 
 8049559:	66 c7 84 24 40 a0 00 	movw   $0x2,0xa040(%esp)
 8049560:	00 02 00 
 8049563:	8b 50 0c             	mov    0xc(%eax),%edx
 8049566:	89 54 24 08          	mov    %edx,0x8(%esp)
 804956a:	8d 94 24 44 a0 00 00 	lea    0xa044(%esp),%edx
 8049571:	89 54 24 04          	mov    %edx,0x4(%esp)
 8049575:	8b 40 10             	mov    0x10(%eax),%eax
 8049578:	8b 00                	mov    (%eax),%eax
 804957a:	89 04 24             	mov    %eax,(%esp)
 804957d:	e8 ee f1 ff ff       	call   8048770 <bcopy@plt>
 8049582:	0f b7 84 24 74 a0 00 	movzwl 0xa074(%esp),%eax
 8049589:	00 
 804958a:	66 c1 c8 08          	ror    $0x8,%ax
 804958e:	66 89 84 24 42 a0 00 	mov    %ax,0xa042(%esp)
 8049595:	00 
 8049596:	c7 44 24 08 10 00 00 	movl   $0x10,0x8(%esp)
 804959d:	00 
 804959e:	89 74 24 04          	mov    %esi,0x4(%esp)
 80495a2:	89 2c 24             	mov    %ebp,(%esp)
 80495a5:	e8 c6 f2 ff ff       	call   8048870 <connect@plt>
 80495aa:	85 c0                	test   %eax,%eax
 80495ac:	79 61                	jns    804960f <submitr+0x1fe>
 80495ae:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 80495b5:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 80495bb:	c7 40 04 72 3a 20 55 	movl   $0x55203a72,0x4(%eax)
 80495c2:	c7 40 08 6e 61 62 6c 	movl   $0x6c62616e,0x8(%eax)
 80495c9:	c7 40 0c 65 20 74 6f 	movl   $0x6f742065,0xc(%eax)
 80495d0:	c7 40 10 20 63 6f 6e 	movl   $0x6e6f6320,0x10(%eax)
 80495d7:	c7 40 14 6e 65 63 74 	movl   $0x7463656e,0x14(%eax)
 80495de:	c7 40 18 20 74 6f 20 	movl   $0x206f7420,0x18(%eax)
 80495e5:	c7 40 1c 74 68 65 20 	movl   $0x20656874,0x1c(%eax)
 80495ec:	c7 40 20 73 65 72 76 	movl   $0x76726573,0x20(%eax)
 80495f3:	66 c7 40 24 65 72    	movw   $0x7265,0x24(%eax)
 80495f9:	c6 40 26 00          	movb   $0x0,0x26(%eax)
 80495fd:	89 2c 24             	mov    %ebp,(%esp)
 8049600:	e8 7b f2 ff ff       	call   8048880 <close@plt>
 8049605:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 804960a:	e9 e9 05 00 00       	jmp    8049bf8 <submitr+0x7e7>
 804960f:	ba ff ff ff ff       	mov    $0xffffffff,%edx
 8049614:	89 df                	mov    %ebx,%edi
 8049616:	b8 00 00 00 00       	mov    $0x0,%eax
 804961b:	89 d1                	mov    %edx,%ecx
 804961d:	f2 ae                	repnz scas %es:(%edi),%al
 804961f:	f7 d1                	not    %ecx
 8049621:	89 ce                	mov    %ecx,%esi
 8049623:	8b bc 24 78 a0 00 00 	mov    0xa078(%esp),%edi
 804962a:	89 d1                	mov    %edx,%ecx
 804962c:	f2 ae                	repnz scas %es:(%edi),%al
 804962e:	89 4c 24 18          	mov    %ecx,0x18(%esp)
 8049632:	8b bc 24 7c a0 00 00 	mov    0xa07c(%esp),%edi
 8049639:	89 d1                	mov    %edx,%ecx
 804963b:	f2 ae                	repnz scas %es:(%edi),%al
 804963d:	f7 d1                	not    %ecx
 804963f:	89 4c 24 1c          	mov    %ecx,0x1c(%esp)
 8049643:	8b bc 24 80 a0 00 00 	mov    0xa080(%esp),%edi
 804964a:	89 d1                	mov    %edx,%ecx
 804964c:	f2 ae                	repnz scas %es:(%edi),%al
 804964e:	8b 44 24 1c          	mov    0x1c(%esp),%eax
 8049652:	2b 44 24 18          	sub    0x18(%esp),%eax
 8049656:	29 c8                	sub    %ecx,%eax
 8049658:	89 c2                	mov    %eax,%edx
 804965a:	8d 44 76 fd          	lea    -0x3(%esi,%esi,2),%eax
 804965e:	8d 44 02 7b          	lea    0x7b(%edx,%eax,1),%eax
 8049662:	3d 00 20 00 00       	cmp    $0x2000,%eax
 8049667:	76 7a                	jbe    80496e3 <submitr+0x2d2>
 8049669:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049670:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 8049676:	c7 40 04 72 3a 20 52 	movl   $0x52203a72,0x4(%eax)
 804967d:	c7 40 08 65 73 75 6c 	movl   $0x6c757365,0x8(%eax)
 8049684:	c7 40 0c 74 20 73 74 	movl   $0x74732074,0xc(%eax)
 804968b:	c7 40 10 72 69 6e 67 	movl   $0x676e6972,0x10(%eax)
 8049692:	c7 40 14 20 74 6f 6f 	movl   $0x6f6f7420,0x14(%eax)
 8049699:	c7 40 18 20 6c 61 72 	movl   $0x72616c20,0x18(%eax)
 80496a0:	c7 40 1c 67 65 2e 20 	movl   $0x202e6567,0x1c(%eax)
 80496a7:	c7 40 20 49 6e 63 72 	movl   $0x72636e49,0x20(%eax)
 80496ae:	c7 40 24 65 61 73 65 	movl   $0x65736165,0x24(%eax)
 80496b5:	c7 40 28 20 53 55 42 	movl   $0x42555320,0x28(%eax)
 80496bc:	c7 40 2c 4d 49 54 52 	movl   $0x5254494d,0x2c(%eax)
 80496c3:	c7 40 30 5f 4d 41 58 	movl   $0x58414d5f,0x30(%eax)
 80496ca:	c7 40 34 42 55 46 00 	movl   $0x465542,0x34(%eax)
 80496d1:	89 2c 24             	mov    %ebp,(%esp)
 80496d4:	e8 a7 f1 ff ff       	call   8048880 <close@plt>
 80496d9:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 80496de:	e9 15 05 00 00       	jmp    8049bf8 <submitr+0x7e7>
 80496e3:	8d 94 24 34 40 00 00 	lea    0x4034(%esp),%edx
 80496ea:	b9 00 08 00 00       	mov    $0x800,%ecx
 80496ef:	b8 00 00 00 00       	mov    $0x0,%eax
 80496f4:	89 d7                	mov    %edx,%edi
 80496f6:	f3 ab                	rep stos %eax,%es:(%edi)
 80496f8:	89 df                	mov    %ebx,%edi
 80496fa:	b9 ff ff ff ff       	mov    $0xffffffff,%ecx
 80496ff:	f2 ae                	repnz scas %es:(%edi),%al
 8049701:	f7 d1                	not    %ecx
 8049703:	83 e9 01             	sub    $0x1,%ecx
 8049706:	89 ce                	mov    %ecx,%esi
 8049708:	0f 84 00 04 00 00    	je     8049b0e <submitr+0x6fd>
 804970e:	89 d7                	mov    %edx,%edi
 8049710:	0f b6 03             	movzbl (%ebx),%eax
 8049713:	3c 2a                	cmp    $0x2a,%al
 8049715:	74 21                	je     8049738 <submitr+0x327>
 8049717:	8d 50 d3             	lea    -0x2d(%eax),%edx
 804971a:	80 fa 01             	cmp    $0x1,%dl
 804971d:	76 19                	jbe    8049738 <submitr+0x327>
 804971f:	3c 5f                	cmp    $0x5f,%al
 8049721:	74 15                	je     8049738 <submitr+0x327>
 8049723:	8d 50 d0             	lea    -0x30(%eax),%edx
 8049726:	80 fa 09             	cmp    $0x9,%dl
 8049729:	76 0d                	jbe    8049738 <submitr+0x327>
 804972b:	89 c2                	mov    %eax,%edx
 804972d:	83 e2 df             	and    $0xffffffdf,%edx
 8049730:	83 ea 41             	sub    $0x41,%edx
 8049733:	80 fa 19             	cmp    $0x19,%dl
 8049736:	77 07                	ja     804973f <submitr+0x32e>
 8049738:	8d 57 01             	lea    0x1(%edi),%edx
 804973b:	88 07                	mov    %al,(%edi)
 804973d:	eb 51                	jmp    8049790 <submitr+0x37f>
 804973f:	3c 20                	cmp    $0x20,%al
 8049741:	75 08                	jne    804974b <submitr+0x33a>
 8049743:	8d 57 01             	lea    0x1(%edi),%edx
 8049746:	c6 07 2b             	movb   $0x2b,(%edi)
 8049749:	eb 45                	jmp    8049790 <submitr+0x37f>
 804974b:	8d 50 e0             	lea    -0x20(%eax),%edx
 804974e:	80 fa 5f             	cmp    $0x5f,%dl
 8049751:	76 08                	jbe    804975b <submitr+0x34a>
 8049753:	3c 09                	cmp    $0x9,%al
 8049755:	0f 85 1d 04 00 00    	jne    8049b78 <submitr+0x767>
 804975b:	0f b6 c0             	movzbl %al,%eax
 804975e:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049762:	c7 44 24 04 4c a8 04 	movl   $0x804a84c,0x4(%esp)
 8049769:	08 
 804976a:	8d 44 24 28          	lea    0x28(%esp),%eax
 804976e:	89 04 24             	mov    %eax,(%esp)
 8049771:	e8 ca f0 ff ff       	call   8048840 <sprintf@plt>
 8049776:	0f b6 44 24 28       	movzbl 0x28(%esp),%eax
 804977b:	88 07                	mov    %al,(%edi)
 804977d:	0f b6 44 24 29       	movzbl 0x29(%esp),%eax
 8049782:	88 47 01             	mov    %al,0x1(%edi)
 8049785:	8d 57 03             	lea    0x3(%edi),%edx
 8049788:	0f b6 44 24 2a       	movzbl 0x2a(%esp),%eax
 804978d:	88 47 02             	mov    %al,0x2(%edi)
 8049790:	83 c3 01             	add    $0x1,%ebx
 8049793:	83 ee 01             	sub    $0x1,%esi
 8049796:	0f 84 72 03 00 00    	je     8049b0e <submitr+0x6fd>
 804979c:	89 d7                	mov    %edx,%edi
 804979e:	e9 6d ff ff ff       	jmp    8049710 <submitr+0x2ff>
 80497a3:	89 5c 24 08          	mov    %ebx,0x8(%esp)
 80497a7:	89 74 24 04          	mov    %esi,0x4(%esp)
 80497ab:	89 2c 24             	mov    %ebp,(%esp)
 80497ae:	e8 3d f0 ff ff       	call   80487f0 <write@plt>
 80497b3:	85 c0                	test   %eax,%eax
 80497b5:	7f 10                	jg     80497c7 <submitr+0x3b6>
 80497b7:	e8 74 f0 ff ff       	call   8048830 <__errno_location@plt>
 80497bc:	83 38 04             	cmpl   $0x4,(%eax)
 80497bf:	90                   	nop
 80497c0:	75 0f                	jne    80497d1 <submitr+0x3c0>
 80497c2:	b8 00 00 00 00       	mov    $0x0,%eax
 80497c7:	01 c6                	add    %eax,%esi
 80497c9:	29 c3                	sub    %eax,%ebx
 80497cb:	75 d6                	jne    80497a3 <submitr+0x392>
 80497cd:	85 ff                	test   %edi,%edi
 80497cf:	79 65                	jns    8049836 <submitr+0x425>
 80497d1:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 80497d8:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 80497de:	c7 40 04 72 3a 20 43 	movl   $0x43203a72,0x4(%eax)
 80497e5:	c7 40 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%eax)
 80497ec:	c7 40 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%eax)
 80497f3:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 80497fa:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 8049801:	c7 40 18 77 72 69 74 	movl   $0x74697277,0x18(%eax)
 8049808:	c7 40 1c 65 20 74 6f 	movl   $0x6f742065,0x1c(%eax)
 804980f:	c7 40 20 20 74 68 65 	movl   $0x65687420,0x20(%eax)
 8049816:	c7 40 24 20 73 65 72 	movl   $0x72657320,0x24(%eax)
 804981d:	c7 40 28 76 65 72 00 	movl   $0x726576,0x28(%eax)
 8049824:	89 2c 24             	mov    %ebp,(%esp)
 8049827:	e8 54 f0 ff ff       	call   8048880 <close@plt>
 804982c:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049831:	e9 c2 03 00 00       	jmp    8049bf8 <submitr+0x7e7>
 8049836:	89 ac 24 34 80 00 00 	mov    %ebp,0x8034(%esp)
 804983d:	c7 84 24 38 80 00 00 	movl   $0x0,0x8038(%esp)
 8049844:	00 00 00 00 
 8049848:	8d 84 24 40 80 00 00 	lea    0x8040(%esp),%eax
 804984f:	89 84 24 3c 80 00 00 	mov    %eax,0x803c(%esp)
 8049856:	b9 00 20 00 00       	mov    $0x2000,%ecx
 804985b:	8d 94 24 34 60 00 00 	lea    0x6034(%esp),%edx
 8049862:	8d 84 24 34 80 00 00 	lea    0x8034(%esp),%eax
 8049869:	e8 9e fa ff ff       	call   804930c <rio_readlineb>
 804986e:	85 c0                	test   %eax,%eax
 8049870:	7f 79                	jg     80498eb <submitr+0x4da>
 8049872:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049879:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 804987f:	c7 40 04 72 3a 20 43 	movl   $0x43203a72,0x4(%eax)
 8049886:	c7 40 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%eax)
 804988d:	c7 40 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%eax)
 8049894:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 804989b:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 80498a2:	c7 40 18 72 65 61 64 	movl   $0x64616572,0x18(%eax)
 80498a9:	c7 40 1c 20 66 69 72 	movl   $0x72696620,0x1c(%eax)
 80498b0:	c7 40 20 73 74 20 68 	movl   $0x68207473,0x20(%eax)
 80498b7:	c7 40 24 65 61 64 65 	movl   $0x65646165,0x24(%eax)
 80498be:	c7 40 28 72 20 66 72 	movl   $0x72662072,0x28(%eax)
 80498c5:	c7 40 2c 6f 6d 20 73 	movl   $0x73206d6f,0x2c(%eax)
 80498cc:	c7 40 30 65 72 76 65 	movl   $0x65767265,0x30(%eax)
 80498d3:	66 c7 40 34 72 00    	movw   $0x72,0x34(%eax)
 80498d9:	89 2c 24             	mov    %ebp,(%esp)
 80498dc:	e8 9f ef ff ff       	call   8048880 <close@plt>
 80498e1:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 80498e6:	e9 0d 03 00 00       	jmp    8049bf8 <submitr+0x7e7>
 80498eb:	8d 44 24 30          	lea    0x30(%esp),%eax
 80498ef:	89 44 24 10          	mov    %eax,0x10(%esp)
 80498f3:	8d 84 24 30 20 00 00 	lea    0x2030(%esp),%eax
 80498fa:	89 44 24 0c          	mov    %eax,0xc(%esp)
 80498fe:	8d 84 24 34 20 00 00 	lea    0x2034(%esp),%eax
 8049905:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049909:	c7 44 24 04 53 a8 04 	movl   $0x804a853,0x4(%esp)
 8049910:	08 
 8049911:	8d 84 24 34 60 00 00 	lea    0x6034(%esp),%eax
 8049918:	89 04 24             	mov    %eax,(%esp)
 804991b:	e8 f0 ee ff ff       	call   8048810 <__isoc99_sscanf@plt>
 8049920:	8b 84 24 30 20 00 00 	mov    0x2030(%esp),%eax
 8049927:	3d c8 00 00 00       	cmp    $0xc8,%eax
 804992c:	0f 84 c1 00 00 00    	je     80499f3 <submitr+0x5e2>
 8049932:	8d 54 24 30          	lea    0x30(%esp),%edx
 8049936:	89 54 24 0c          	mov    %edx,0xc(%esp)
 804993a:	89 44 24 08          	mov    %eax,0x8(%esp)
 804993e:	c7 44 24 04 64 a7 04 	movl   $0x804a764,0x4(%esp)
 8049945:	08 
 8049946:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 804994d:	89 04 24             	mov    %eax,(%esp)
 8049950:	e8 eb ee ff ff       	call   8048840 <sprintf@plt>
 8049955:	89 2c 24             	mov    %ebp,(%esp)
 8049958:	e8 23 ef ff ff       	call   8048880 <close@plt>
 804995d:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049962:	e9 91 02 00 00       	jmp    8049bf8 <submitr+0x7e7>
 8049967:	b9 00 20 00 00       	mov    $0x2000,%ecx
 804996c:	8d 94 24 34 60 00 00 	lea    0x6034(%esp),%edx
 8049973:	8d 84 24 34 80 00 00 	lea    0x8034(%esp),%eax
 804997a:	e8 8d f9 ff ff       	call   804930c <rio_readlineb>
 804997f:	85 c0                	test   %eax,%eax
 8049981:	7f 70                	jg     80499f3 <submitr+0x5e2>
 8049983:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 804998a:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 8049990:	c7 40 04 72 3a 20 43 	movl   $0x43203a72,0x4(%eax)
 8049997:	c7 40 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%eax)
 804999e:	c7 40 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%eax)
 80499a5:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 80499ac:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 80499b3:	c7 40 18 72 65 61 64 	movl   $0x64616572,0x18(%eax)
 80499ba:	c7 40 1c 20 68 65 61 	movl   $0x61656820,0x1c(%eax)
 80499c1:	c7 40 20 64 65 72 73 	movl   $0x73726564,0x20(%eax)
 80499c8:	c7 40 24 20 66 72 6f 	movl   $0x6f726620,0x24(%eax)
 80499cf:	c7 40 28 6d 20 73 65 	movl   $0x6573206d,0x28(%eax)
 80499d6:	c7 40 2c 72 76 65 72 	movl   $0x72657672,0x2c(%eax)
 80499dd:	c6 40 30 00          	movb   $0x0,0x30(%eax)
 80499e1:	89 2c 24             	mov    %ebp,(%esp)
 80499e4:	e8 97 ee ff ff       	call   8048880 <close@plt>
 80499e9:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 80499ee:	e9 05 02 00 00       	jmp    8049bf8 <submitr+0x7e7>
 80499f3:	80 bc 24 34 60 00 00 	cmpb   $0xd,0x6034(%esp)
 80499fa:	0d 
 80499fb:	0f 85 66 ff ff ff    	jne    8049967 <submitr+0x556>
 8049a01:	80 bc 24 35 60 00 00 	cmpb   $0xa,0x6035(%esp)
 8049a08:	0a 
 8049a09:	0f 85 58 ff ff ff    	jne    8049967 <submitr+0x556>
 8049a0f:	80 bc 24 36 60 00 00 	cmpb   $0x0,0x6036(%esp)
 8049a16:	00 
 8049a17:	0f 85 4a ff ff ff    	jne    8049967 <submitr+0x556>
 8049a1d:	b9 00 20 00 00       	mov    $0x2000,%ecx
 8049a22:	8d 94 24 34 60 00 00 	lea    0x6034(%esp),%edx
 8049a29:	8d 84 24 34 80 00 00 	lea    0x8034(%esp),%eax
 8049a30:	e8 d7 f8 ff ff       	call   804930c <rio_readlineb>
 8049a35:	85 c0                	test   %eax,%eax
 8049a37:	7f 7a                	jg     8049ab3 <submitr+0x6a2>
 8049a39:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049a40:	c7 00 45 72 72 6f    	movl   $0x6f727245,(%eax)
 8049a46:	c7 40 04 72 3a 20 43 	movl   $0x43203a72,0x4(%eax)
 8049a4d:	c7 40 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%eax)
 8049a54:	c7 40 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%eax)
 8049a5b:	c7 40 10 61 62 6c 65 	movl   $0x656c6261,0x10(%eax)
 8049a62:	c7 40 14 20 74 6f 20 	movl   $0x206f7420,0x14(%eax)
 8049a69:	c7 40 18 72 65 61 64 	movl   $0x64616572,0x18(%eax)
 8049a70:	c7 40 1c 20 73 74 61 	movl   $0x61747320,0x1c(%eax)
 8049a77:	c7 40 20 74 75 73 20 	movl   $0x20737574,0x20(%eax)
 8049a7e:	c7 40 24 6d 65 73 73 	movl   $0x7373656d,0x24(%eax)
 8049a85:	c7 40 28 61 67 65 20 	movl   $0x20656761,0x28(%eax)
 8049a8c:	c7 40 2c 66 72 6f 6d 	movl   $0x6d6f7266,0x2c(%eax)
 8049a93:	c7 40 30 20 73 65 72 	movl   $0x72657320,0x30(%eax)
 8049a9a:	c7 40 34 76 65 72 00 	movl   $0x726576,0x34(%eax)
 8049aa1:	89 2c 24             	mov    %ebp,(%esp)
 8049aa4:	e8 d7 ed ff ff       	call   8048880 <close@plt>
 8049aa9:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049aae:	e9 45 01 00 00       	jmp    8049bf8 <submitr+0x7e7>
 8049ab3:	8d 84 24 34 60 00 00 	lea    0x6034(%esp),%eax
 8049aba:	89 44 24 04          	mov    %eax,0x4(%esp)
 8049abe:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049ac5:	89 04 24             	mov    %eax,(%esp)
 8049ac8:	e8 b3 ec ff ff       	call   8048780 <strcpy@plt>
 8049acd:	89 2c 24             	mov    %ebp,(%esp)
 8049ad0:	e8 ab ed ff ff       	call   8048880 <close@plt>
 8049ad5:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049adc:	0f b6 00             	movzbl (%eax),%eax
 8049adf:	83 e8 4f             	sub    $0x4f,%eax
 8049ae2:	75 1b                	jne    8049aff <submitr+0x6ee>
 8049ae4:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049aeb:	0f b6 40 01          	movzbl 0x1(%eax),%eax
 8049aef:	83 e8 4b             	sub    $0x4b,%eax
 8049af2:	75 0b                	jne    8049aff <submitr+0x6ee>
 8049af4:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049afb:	0f b6 40 02          	movzbl 0x2(%eax),%eax
 8049aff:	85 c0                	test   %eax,%eax
 8049b01:	0f 95 c0             	setne  %al
 8049b04:	0f b6 c0             	movzbl %al,%eax
 8049b07:	f7 d8                	neg    %eax
 8049b09:	e9 ea 00 00 00       	jmp    8049bf8 <submitr+0x7e7>
 8049b0e:	8d 84 24 34 40 00 00 	lea    0x4034(%esp),%eax
 8049b15:	89 44 24 14          	mov    %eax,0x14(%esp)
 8049b19:	8b 84 24 80 a0 00 00 	mov    0xa080(%esp),%eax
 8049b20:	89 44 24 10          	mov    %eax,0x10(%esp)
 8049b24:	8b 84 24 7c a0 00 00 	mov    0xa07c(%esp),%eax
 8049b2b:	89 44 24 0c          	mov    %eax,0xc(%esp)
 8049b2f:	8b 84 24 78 a0 00 00 	mov    0xa078(%esp),%eax
 8049b36:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049b3a:	c7 44 24 04 94 a7 04 	movl   $0x804a794,0x4(%esp)
 8049b41:	08 
 8049b42:	8d bc 24 34 60 00 00 	lea    0x6034(%esp),%edi
 8049b49:	89 3c 24             	mov    %edi,(%esp)
 8049b4c:	e8 ef ec ff ff       	call   8048840 <sprintf@plt>
 8049b51:	b8 00 00 00 00       	mov    $0x0,%eax
 8049b56:	b9 ff ff ff ff       	mov    $0xffffffff,%ecx
 8049b5b:	f2 ae                	repnz scas %es:(%edi),%al
 8049b5d:	f7 d1                	not    %ecx
 8049b5f:	83 e9 01             	sub    $0x1,%ecx
 8049b62:	89 cf                	mov    %ecx,%edi
 8049b64:	0f 84 cc fc ff ff    	je     8049836 <submitr+0x425>
 8049b6a:	89 cb                	mov    %ecx,%ebx
 8049b6c:	8d b4 24 34 60 00 00 	lea    0x6034(%esp),%esi
 8049b73:	e9 2b fc ff ff       	jmp    80497a3 <submitr+0x392>
 8049b78:	8b bc 24 88 a0 00 00 	mov    0xa088(%esp),%edi
 8049b7f:	be e0 a7 04 08       	mov    $0x804a7e0,%esi
 8049b84:	b8 43 00 00 00       	mov    $0x43,%eax
 8049b89:	f7 c7 01 00 00 00    	test   $0x1,%edi
 8049b8f:	74 1d                	je     8049bae <submitr+0x79d>
 8049b91:	0f b6 05 e0 a7 04 08 	movzbl 0x804a7e0,%eax
 8049b98:	88 07                	mov    %al,(%edi)
 8049b9a:	8b 84 24 88 a0 00 00 	mov    0xa088(%esp),%eax
 8049ba1:	8d 78 01             	lea    0x1(%eax),%edi
 8049ba4:	be e1 a7 04 08       	mov    $0x804a7e1,%esi
 8049ba9:	b8 42 00 00 00       	mov    $0x42,%eax
 8049bae:	f7 c7 02 00 00 00    	test   $0x2,%edi
 8049bb4:	74 0f                	je     8049bc5 <submitr+0x7b4>
 8049bb6:	0f b7 16             	movzwl (%esi),%edx
 8049bb9:	66 89 17             	mov    %dx,(%edi)
 8049bbc:	83 c7 02             	add    $0x2,%edi
 8049bbf:	83 c6 02             	add    $0x2,%esi
 8049bc2:	83 e8 02             	sub    $0x2,%eax
 8049bc5:	89 c1                	mov    %eax,%ecx
 8049bc7:	c1 e9 02             	shr    $0x2,%ecx
 8049bca:	f3 a5                	rep movsl %ds:(%esi),%es:(%edi)
 8049bcc:	ba 00 00 00 00       	mov    $0x0,%edx
 8049bd1:	a8 02                	test   $0x2,%al
 8049bd3:	74 0b                	je     8049be0 <submitr+0x7cf>
 8049bd5:	0f b7 16             	movzwl (%esi),%edx
 8049bd8:	66 89 17             	mov    %dx,(%edi)
 8049bdb:	ba 02 00 00 00       	mov    $0x2,%edx
 8049be0:	a8 01                	test   $0x1,%al
 8049be2:	74 07                	je     8049beb <submitr+0x7da>
 8049be4:	0f b6 04 16          	movzbl (%esi,%edx,1),%eax
 8049be8:	88 04 17             	mov    %al,(%edi,%edx,1)
 8049beb:	89 2c 24             	mov    %ebp,(%esp)
 8049bee:	e8 8d ec ff ff       	call   8048880 <close@plt>
 8049bf3:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049bf8:	81 c4 5c a0 00 00    	add    $0xa05c,%esp
 8049bfe:	5b                   	pop    %ebx
 8049bff:	5e                   	pop    %esi
 8049c00:	5f                   	pop    %edi
 8049c01:	5d                   	pop    %ebp
 8049c02:	c3                   	ret    

08049c03 <init_timeout>:
 8049c03:	53                   	push   %ebx
 8049c04:	83 ec 18             	sub    $0x18,%esp
 8049c07:	8b 5c 24 20          	mov    0x20(%esp),%ebx
 8049c0b:	85 db                	test   %ebx,%ebx
 8049c0d:	74 26                	je     8049c35 <init_timeout+0x32>
 8049c0f:	c7 44 24 04 e0 92 04 	movl   $0x80492e0,0x4(%esp)
 8049c16:	08 
 8049c17:	c7 04 24 0e 00 00 00 	movl   $0xe,(%esp)
 8049c1e:	e8 1d eb ff ff       	call   8048740 <signal@plt>
 8049c23:	85 db                	test   %ebx,%ebx
 8049c25:	b8 00 00 00 00       	mov    $0x0,%eax
 8049c2a:	0f 48 d8             	cmovs  %eax,%ebx
 8049c2d:	89 1c 24             	mov    %ebx,(%esp)
 8049c30:	e8 2b eb ff ff       	call   8048760 <alarm@plt>
 8049c35:	83 c4 18             	add    $0x18,%esp
 8049c38:	5b                   	pop    %ebx
 8049c39:	c3                   	ret    

08049c3a <init_driver>:
 8049c3a:	57                   	push   %edi
 8049c3b:	56                   	push   %esi
 8049c3c:	53                   	push   %ebx
 8049c3d:	83 ec 20             	sub    $0x20,%esp
 8049c40:	8b 74 24 30          	mov    0x30(%esp),%esi
 8049c44:	c7 44 24 04 01 00 00 	movl   $0x1,0x4(%esp)
 8049c4b:	00 
 8049c4c:	c7 04 24 0d 00 00 00 	movl   $0xd,(%esp)
 8049c53:	e8 e8 ea ff ff       	call   8048740 <signal@plt>
 8049c58:	c7 44 24 04 01 00 00 	movl   $0x1,0x4(%esp)
 8049c5f:	00 
 8049c60:	c7 04 24 1d 00 00 00 	movl   $0x1d,(%esp)
 8049c67:	e8 d4 ea ff ff       	call   8048740 <signal@plt>
 8049c6c:	c7 44 24 04 01 00 00 	movl   $0x1,0x4(%esp)
 8049c73:	00 
 8049c74:	c7 04 24 1d 00 00 00 	movl   $0x1d,(%esp)
 8049c7b:	e8 c0 ea ff ff       	call   8048740 <signal@plt>
 8049c80:	c7 44 24 08 00 00 00 	movl   $0x0,0x8(%esp)
 8049c87:	00 
 8049c88:	c7 44 24 04 01 00 00 	movl   $0x1,0x4(%esp)
 8049c8f:	00 
 8049c90:	c7 04 24 02 00 00 00 	movl   $0x2,(%esp)
 8049c97:	e8 b4 eb ff ff       	call   8048850 <socket@plt>
 8049c9c:	89 c3                	mov    %eax,%ebx
 8049c9e:	85 c0                	test   %eax,%eax
 8049ca0:	79 4e                	jns    8049cf0 <init_driver+0xb6>
 8049ca2:	c7 06 45 72 72 6f    	movl   $0x6f727245,(%esi)
 8049ca8:	c7 46 04 72 3a 20 43 	movl   $0x43203a72,0x4(%esi)
 8049caf:	c7 46 08 6c 69 65 6e 	movl   $0x6e65696c,0x8(%esi)
 8049cb6:	c7 46 0c 74 20 75 6e 	movl   $0x6e752074,0xc(%esi)
 8049cbd:	c7 46 10 61 62 6c 65 	movl   $0x656c6261,0x10(%esi)
 8049cc4:	c7 46 14 20 74 6f 20 	movl   $0x206f7420,0x14(%esi)
 8049ccb:	c7 46 18 63 72 65 61 	movl   $0x61657263,0x18(%esi)
 8049cd2:	c7 46 1c 74 65 20 73 	movl   $0x73206574,0x1c(%esi)
 8049cd9:	c7 46 20 6f 63 6b 65 	movl   $0x656b636f,0x20(%esi)
 8049ce0:	66 c7 46 24 74 00    	movw   $0x74,0x24(%esi)
 8049ce6:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049ceb:	e9 1b 01 00 00       	jmp    8049e0b <init_driver+0x1d1>
 8049cf0:	c7 04 24 e0 a3 04 08 	movl   $0x804a3e0,(%esp)
 8049cf7:	e8 64 eb ff ff       	call   8048860 <gethostbyname@plt>
 8049cfc:	85 c0                	test   %eax,%eax
 8049cfe:	75 68                	jne    8049d68 <init_driver+0x12e>
 8049d00:	c7 06 45 72 72 6f    	movl   $0x6f727245,(%esi)
 8049d06:	c7 46 04 72 3a 20 44 	movl   $0x44203a72,0x4(%esi)
 8049d0d:	c7 46 08 4e 53 20 69 	movl   $0x6920534e,0x8(%esi)
 8049d14:	c7 46 0c 73 20 75 6e 	movl   $0x6e752073,0xc(%esi)
 8049d1b:	c7 46 10 61 62 6c 65 	movl   $0x656c6261,0x10(%esi)
 8049d22:	c7 46 14 20 74 6f 20 	movl   $0x206f7420,0x14(%esi)
 8049d29:	c7 46 18 72 65 73 6f 	movl   $0x6f736572,0x18(%esi)
 8049d30:	c7 46 1c 6c 76 65 20 	movl   $0x2065766c,0x1c(%esi)
 8049d37:	c7 46 20 73 65 72 76 	movl   $0x76726573,0x20(%esi)
 8049d3e:	c7 46 24 65 72 20 61 	movl   $0x61207265,0x24(%esi)
 8049d45:	c7 46 28 64 64 72 65 	movl   $0x65726464,0x28(%esi)
 8049d4c:	66 c7 46 2c 73 73    	movw   $0x7373,0x2c(%esi)
 8049d52:	c6 46 2e 00          	movb   $0x0,0x2e(%esi)
 8049d56:	89 1c 24             	mov    %ebx,(%esp)
 8049d59:	e8 22 eb ff ff       	call   8048880 <close@plt>
 8049d5e:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049d63:	e9 a3 00 00 00       	jmp    8049e0b <init_driver+0x1d1>
 8049d68:	8d 7c 24 10          	lea    0x10(%esp),%edi
 8049d6c:	c7 44 24 10 00 00 00 	movl   $0x0,0x10(%esp)
 8049d73:	00 
 8049d74:	c7 44 24 14 00 00 00 	movl   $0x0,0x14(%esp)
 8049d7b:	00 
 8049d7c:	c7 44 24 18 00 00 00 	movl   $0x0,0x18(%esp)
 8049d83:	00 
 8049d84:	c7 44 24 1c 00 00 00 	movl   $0x0,0x1c(%esp)
 8049d8b:	00 
 8049d8c:	66 c7 44 24 10 02 00 	movw   $0x2,0x10(%esp)
 8049d93:	8b 50 0c             	mov    0xc(%eax),%edx
 8049d96:	89 54 24 08          	mov    %edx,0x8(%esp)
 8049d9a:	8d 54 24 14          	lea    0x14(%esp),%edx
 8049d9e:	89 54 24 04          	mov    %edx,0x4(%esp)
 8049da2:	8b 40 10             	mov    0x10(%eax),%eax
 8049da5:	8b 00                	mov    (%eax),%eax
 8049da7:	89 04 24             	mov    %eax,(%esp)
 8049daa:	e8 c1 e9 ff ff       	call   8048770 <bcopy@plt>
 8049daf:	66 c7 44 24 12 43 31 	movw   $0x3143,0x12(%esp)
 8049db6:	c7 44 24 08 10 00 00 	movl   $0x10,0x8(%esp)
 8049dbd:	00 
 8049dbe:	89 7c 24 04          	mov    %edi,0x4(%esp)
 8049dc2:	89 1c 24             	mov    %ebx,(%esp)
 8049dc5:	e8 a6 ea ff ff       	call   8048870 <connect@plt>
 8049dca:	85 c0                	test   %eax,%eax
 8049dcc:	79 27                	jns    8049df5 <init_driver+0x1bb>
 8049dce:	c7 44 24 08 e0 a3 04 	movl   $0x804a3e0,0x8(%esp)
 8049dd5:	08 
 8049dd6:	c7 44 24 04 24 a8 04 	movl   $0x804a824,0x4(%esp)
 8049ddd:	08 
 8049dde:	89 34 24             	mov    %esi,(%esp)
 8049de1:	e8 5a ea ff ff       	call   8048840 <sprintf@plt>
 8049de6:	89 1c 24             	mov    %ebx,(%esp)
 8049de9:	e8 92 ea ff ff       	call   8048880 <close@plt>
 8049dee:	b8 ff ff ff ff       	mov    $0xffffffff,%eax
 8049df3:	eb 16                	jmp    8049e0b <init_driver+0x1d1>
 8049df5:	89 1c 24             	mov    %ebx,(%esp)
 8049df8:	e8 83 ea ff ff       	call   8048880 <close@plt>
 8049dfd:	66 c7 06 4f 4b       	movw   $0x4b4f,(%esi)
 8049e02:	c6 46 02 00          	movb   $0x0,0x2(%esi)
 8049e06:	b8 00 00 00 00       	mov    $0x0,%eax
 8049e0b:	83 c4 20             	add    $0x20,%esp
 8049e0e:	5b                   	pop    %ebx
 8049e0f:	5e                   	pop    %esi
 8049e10:	5f                   	pop    %edi
 8049e11:	c3                   	ret    

08049e12 <driver_post>:
 8049e12:	53                   	push   %ebx
 8049e13:	83 ec 28             	sub    $0x28,%esp
 8049e16:	8b 44 24 30          	mov    0x30(%esp),%eax
 8049e1a:	8b 5c 24 3c          	mov    0x3c(%esp),%ebx
 8049e1e:	83 7c 24 38 00       	cmpl   $0x0,0x38(%esp)
 8049e23:	74 24                	je     8049e49 <driver_post+0x37>
 8049e25:	8b 44 24 34          	mov    0x34(%esp),%eax
 8049e29:	89 44 24 04          	mov    %eax,0x4(%esp)
 8049e2d:	c7 04 24 64 a8 04 08 	movl   $0x804a864,(%esp)
 8049e34:	e8 c7 e8 ff ff       	call   8048700 <printf@plt>
 8049e39:	66 c7 03 4f 4b       	movw   $0x4b4f,(%ebx)
 8049e3e:	c6 43 02 00          	movb   $0x0,0x2(%ebx)
 8049e42:	b8 00 00 00 00       	mov    $0x0,%eax
 8049e47:	eb 4d                	jmp    8049e96 <driver_post+0x84>
 8049e49:	85 c0                	test   %eax,%eax
 8049e4b:	74 3b                	je     8049e88 <driver_post+0x76>
 8049e4d:	80 38 00             	cmpb   $0x0,(%eax)
 8049e50:	74 36                	je     8049e88 <driver_post+0x76>
 8049e52:	89 5c 24 18          	mov    %ebx,0x18(%esp)
 8049e56:	8b 54 24 34          	mov    0x34(%esp),%edx
 8049e5a:	89 54 24 14          	mov    %edx,0x14(%esp)
 8049e5e:	c7 44 24 10 7b a8 04 	movl   $0x804a87b,0x10(%esp)
 8049e65:	08 
 8049e66:	89 44 24 0c          	mov    %eax,0xc(%esp)
 8049e6a:	c7 44 24 08 84 a8 04 	movl   $0x804a884,0x8(%esp)
 8049e71:	08 
 8049e72:	c7 44 24 04 31 43 00 	movl   $0x4331,0x4(%esp)
 8049e79:	00 
 8049e7a:	c7 04 24 e0 a3 04 08 	movl   $0x804a3e0,(%esp)
 8049e81:	e8 8b f5 ff ff       	call   8049411 <submitr>
 8049e86:	eb 0e                	jmp    8049e96 <driver_post+0x84>
 8049e88:	66 c7 03 4f 4b       	movw   $0x4b4f,(%ebx)
 8049e8d:	c6 43 02 00          	movb   $0x0,0x2(%ebx)
 8049e91:	b8 00 00 00 00       	mov    $0x0,%eax
 8049e96:	83 c4 28             	add    $0x28,%esp
 8049e99:	5b                   	pop    %ebx
 8049e9a:	c3                   	ret    
 8049e9b:	66 90                	xchg   %ax,%ax
 8049e9d:	66 90                	xchg   %ax,%ax
 8049e9f:	90                   	nop

08049ea0 <__libc_csu_init>:
 8049ea0:	55                   	push   %ebp
 8049ea1:	57                   	push   %edi
 8049ea2:	31 ff                	xor    %edi,%edi
 8049ea4:	56                   	push   %esi
 8049ea5:	53                   	push   %ebx
 8049ea6:	e8 35 ea ff ff       	call   80488e0 <__x86.get_pc_thunk.bx>
 8049eab:	81 c3 55 21 00 00    	add    $0x2155,%ebx
 8049eb1:	83 ec 1c             	sub    $0x1c,%esp
 8049eb4:	8b 6c 24 30          	mov    0x30(%esp),%ebp
 8049eb8:	8d b3 0c ff ff ff    	lea    -0xf4(%ebx),%esi
 8049ebe:	e8 f9 e7 ff ff       	call   80486bc <_init>
 8049ec3:	8d 83 08 ff ff ff    	lea    -0xf8(%ebx),%eax
 8049ec9:	29 c6                	sub    %eax,%esi
 8049ecb:	c1 fe 02             	sar    $0x2,%esi
 8049ece:	85 f6                	test   %esi,%esi
 8049ed0:	74 27                	je     8049ef9 <__libc_csu_init+0x59>
 8049ed2:	8d b6 00 00 00 00    	lea    0x0(%esi),%esi
 8049ed8:	8b 44 24 38          	mov    0x38(%esp),%eax
 8049edc:	89 2c 24             	mov    %ebp,(%esp)
 8049edf:	89 44 24 08          	mov    %eax,0x8(%esp)
 8049ee3:	8b 44 24 34          	mov    0x34(%esp),%eax
 8049ee7:	89 44 24 04          	mov    %eax,0x4(%esp)
 8049eeb:	ff 94 bb 08 ff ff ff 	call   *-0xf8(%ebx,%edi,4)
 8049ef2:	83 c7 01             	add    $0x1,%edi
 8049ef5:	39 f7                	cmp    %esi,%edi
 8049ef7:	75 df                	jne    8049ed8 <__libc_csu_init+0x38>
 8049ef9:	83 c4 1c             	add    $0x1c,%esp
 8049efc:	5b                   	pop    %ebx
 8049efd:	5e                   	pop    %esi
 8049efe:	5f                   	pop    %edi
 8049eff:	5d                   	pop    %ebp
 8049f00:	c3                   	ret    
 8049f01:	eb 0d                	jmp    8049f10 <__libc_csu_fini>
 8049f03:	90                   	nop
 8049f04:	90                   	nop
 8049f05:	90                   	nop
 8049f06:	90                   	nop
 8049f07:	90                   	nop
 8049f08:	90                   	nop
 8049f09:	90                   	nop
 8049f0a:	90                   	nop
 8049f0b:	90                   	nop
 8049f0c:	90                   	nop
 8049f0d:	90                   	nop
 8049f0e:	90                   	nop
 8049f0f:	90                   	nop

08049f10 <__libc_csu_fini>:
 8049f10:	f3 c3                	repz ret 

Disassembly of section .fini:

08049f14 <_fini>:
 8049f14:	53                   	push   %ebx
 8049f15:	83 ec 08             	sub    $0x8,%esp
 8049f18:	e8 c3 e9 ff ff       	call   80488e0 <__x86.get_pc_thunk.bx>
 8049f1d:	81 c3 e3 20 00 00    	add    $0x20e3,%ebx
 8049f23:	83 c4 08             	add    $0x8,%esp
 8049f26:	5b                   	pop    %ebx
 8049f27:	c3                   	ret    
```
