---
title: Desinstalar a versão autônoma do Construtor de Relatórios (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581689"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a>Desinstalar a versão autônoma do Construtor de Relatórios (Construtor de Relatórios)
  É possível desinstalar a versão autônoma do Construtor de Relatórios no painel de controle ou na linha de comando. Não é possível desinstalar a versão [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] do Construtor de Relatórios sem desinstalar o [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].  
  
 A desinstalação do Construtor de Relatórios a partir da linha de comando usa a sintaxe idêntica à sintaxe usada para instalar o Construtor de Relatórios, exceto pelo uso da opção /x em vez da opção /i. As linhas de comando de desinstalação também podem incluir a opção /quiet e outras opções padrão. Se o pacote do Windows Installer do Construtor de Relatórios (ReportBuilder3_x86.msi) tiver sido removido, não será possível usar a linha de comando para desinstalar facilmente o Construtor de Relatórios. Para saber mais sobre como pode remover o Construtor de Relatórios usando sua GUID, consulte a documentação do programa msiexec na biblioteca do MSDN.  
  
 Se as pastas usadas pelo Construtor de Relatórios incluírem arquivos personalizados, as pastas e os arquivos serão preservados quando o Construtor de Relatórios for removido. Apenas os arquivos do Construtor de Relatórios serão removidos.  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a>Para desinstalar o Construtor de Relatórios a partir do painel de controle.  
  
1.  No menu **Iniciar** , clique em **Painel de Controle**.  
  
2.  No Painel de Controle, clique em **Programas e Recursos**.  
  
3.  Localize o  Construtor de Relatórios na lista Nome e clique nele.  
  
4.  Clique em **Desinstalar**.  
  
5.  Se solicitado a confirmar a desinstalação do Construtor de Relatórios, clique em **Sim**.  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a>Para desinstalar o Construtor de Relatórios a partir da linha de comando  
  
1.  No menu **Iniciar** , clique em **Executar**.  
  
2.  Na caixa de texto **abrir** , digite`cmd.`  
  
3.  Na janela do prompt de comando, navegue até pasta com ReportBuilder3_x86.msi.  
  
4.  Digite uma linha de comando básica, como a seguir:  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 Se você puder incluir o registro em log, use uma linha de comando como a seguinte:  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  Pressione **Enter**.  
  
## <a name="see-also"></a>Consulte Também  
 [Instalar, desinstalar e Construtor de Relatórios suporte](../install-uninstall-and-report-builder-support.md)   
 [Instale a versão autônoma do Construtor de Relatórios &#40;Construtor de Relatórios&#41;](install-report-builder.md)  
  
  
