all: common XP W7 W8 gui

common: exports imports dll gaps tls bound entrypoint down many misc resource delay relocs dotnet load_config

exports: ownexports.exe ownexports2.exe exportsdata.exe exportobf.exe exports_doc.exe exports_order.exe \
    ownexportsdot.exe

many: 96emptysections.exe 96workingsections.exe bigSoRD.exe

dll: dll.dll dll-ld.exe dll-dynld.exe dllweirdexp.dll dllweirdexp-ld.exe dllemptyexp.dll \
    dllemptyexp-ld.exe dllord.dll dllord-ld.exe dll-dynunicld.exe dllnoreloc.dll dllnoreloc-ld.exe \
    dllnoexp.dll dllnoexp-dynld.exe dllfw.dll dllfw-ld.exe dllfwloop.dll dllfwloop-ld.exe \
    dll-webdavld.exe dupsec.exe secinsec.exe bigib.exe dllnomain.dll dllnomain-ld.exe \
    dllnomain2.dll dllnomain2-dynld.exe dllnullep.dll dllnullep-ld.exe dllnullep-dynld.exe \
    dllnegep.dll dllnegep-ld.exe ctxt.dll ctxt-ld.exe \
    dllfakess.dll dllfakess-ld.exe dllfakess-dynld.exe \
    dllmaxvals.dll dllmaxvals-ld.exe dllmaxvals-dynld.exe

relocs: ibkernel.exe reloccrypt.exe ibkmanual.exe ibreloc.exe fakerelocs.exe lfanew_relocW7.exe \
    lfanew_relocXP.exe relocsstripped.exe relocsstripped64.exe skippeddynbase.exe reloc9.exe \
    reloc4.exe relocOSdet.exe

misc: normal.exe truncatedlast.exe pdf.exe tiny.exe bigsec.exe shuffledsect.exe truncsectbl.exe \
    quine.exe bigalign.exe foldedhdr.exe compiled.exe duphead.exe \
    no0code.exe fakeregs.exe fakeregslib.dll multiss.exe multiss_gui.exe no_dd.exe \
    maxvals.exe pdf_zip_pe.exe winver.exe weirdsord.exe hdrcode.exe mini.exe \
    dump_imports.exe nullvirt.exe safeseh.exe lfanew_relocW7.exe \
    lfanew_relocXP.exe safeseh_fly.exe signature.exe standard.exe \
    dep.exe no_dep.exe no_seh.exe memshared.dll memshared-ld.exe  aslr.dll aslr-ld.exe \
    debug.exe copyright.exe hdrdata.exe no_dd64.exe \
    lowsubsys.exe tinydll.dll tinydll-ld.exe ddsect.exe lowaldiff.exe

down: appendedsecttbl.exe appendedhdr.exe footer.exe bottomsecttbl.exe

gui: gui.exe tinygui.exe

entrypoint: virtEP.exe dllextep.dll dllextep-ld.exe nullEP.exe

bound: dllbound.dll dllbound-ld.exe dllbound-redirld.exe

tls: tls.exe tls_obfuscation.exe tls_import.exe mz.exe tls_onthefly.exe tls_aoi.exe \
    tls_aoiOSDET.exe tls_exiting.exe tls_noEP.exe tls_reloc.exe tls_k32.exe tls_virtEP.exe \
    tls64.exe

delay: delayimports.exe delaycorrupt.exe delayfake.exe

gaps: appendeddata.exe hiddenappdata1.exe hiddenappdata2.exe slackspace.exe virtgap.exe

resource: manifest resource.exe resource2.exe reshdr.exe namedresource.exe resourceloop.exe \
    resource_string.exe d_resource-ld.exe d_resource.dll version resource_icon.exe

manifest: manifest.exe manifest_bsod.exe manifest_broken.exe

version: version_mini.exe version_std.exe version_cust.exe

load_config: ldrsnaps.exe ldrsnaps64.exe cfgbogus.exe dllcfgdup.dll dllcfgdup-dynld.exe \
    ss63.exe ss63nocookie.exe

imports: imports.exe imports_noint.exe imports_noext.exe imports_mixed.exe impbyord.exe \
    imports_badterm.exe imports_vterm.exe imports_nothunk.exe imports_multidesc.exe \
    imports_iatindesc.exe imports_virtdesc.exe importshint.exe nothing.dll \
	nothing-ld.exe d_tiny.dll d_tiny-ld.exe d_nonnull.dll d_nonnull-ld.exe sc.exe \
	hard_imports.exe imports_corruptedIAT.exe imports_bogusIAT.exe imports_nnIAT.exe

XP: tinyXP.exe maxsecXP.exe nosectionXP.exe nullSOH-XP.exe virtsectblXP.exe tinydllXP.dll \
    tinydllXP-ld.exe ibnullXP.exe dllbound-redirldXP.exe dllbound2.dll reloccryptXP.exe \
    dosZMXP.exe driver.sys tinydrivXP.sys virtrelocXP.exe exe2pe.exe imports_tinyXP.exe \
    importsdotXP.exe

W7: tinyW7.exe tinyW7x64.exe tinyW7_3264.exe maxsec_lowaligW7.exe nosectionW7.exe maxsecW7.exe \
    appsectableW7.exe apphdrW7.exe foldedhdrW7.exe normal64.exe 65535sects.exe imports_apimsW7.exe \
    ibrelocW7.exe ibknoreloc64.exe imports_tinyW7.exe manyimportsW7.exe imports_relocW7.exe \
	exceptions.exe seh_change64.exe

W8: reloccryptW8.exe

dotnet: tinynet.exe dotnet20.exe mscoree.exe fakenet.exe

multiss_gui.exe: multiss.exe
	c:\python26\python multiss.py

65535sects.exe: ..\mkpe.py
	c:\python26\python ..\mkpe.py 65535

%.exe: ..\%.asm
	yasm -o $@ $<

%.dll: ..\%.asm
	yasm -o $@ $<

%.sys: ..\%.asm
	yasm -o $@ $<
	c:\python26\python fixsum.py $@
