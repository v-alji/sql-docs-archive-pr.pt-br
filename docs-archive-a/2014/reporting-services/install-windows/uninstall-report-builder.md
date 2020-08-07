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
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="82fa2-102">Desinstalar a versão autônoma do Construtor de Relatórios (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="82fa2-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="82fa2-103">É possível desinstalar a versão autônoma do Construtor de Relatórios no painel de controle ou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="82fa2-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="82fa2-104">Não é possível desinstalar a versão [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] do Construtor de Relatórios sem desinstalar o [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82fa2-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="82fa2-105">A desinstalação do Construtor de Relatórios a partir da linha de comando usa a sintaxe idêntica à sintaxe usada para instalar o Construtor de Relatórios, exceto pelo uso da opção /x em vez da opção /i.</span><span class="sxs-lookup"><span data-stu-id="82fa2-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="82fa2-106">As linhas de comando de desinstalação também podem incluir a opção /quiet e outras opções padrão.</span><span class="sxs-lookup"><span data-stu-id="82fa2-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="82fa2-107">Se o pacote do Windows Installer do Construtor de Relatórios (ReportBuilder3_x86.msi) tiver sido removido, não será possível usar a linha de comando para desinstalar facilmente o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="82fa2-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="82fa2-108">Para saber mais sobre como pode remover o Construtor de Relatórios usando sua GUID, consulte a documentação do programa msiexec na biblioteca do MSDN.</span><span class="sxs-lookup"><span data-stu-id="82fa2-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="82fa2-109">Se as pastas usadas pelo Construtor de Relatórios incluírem arquivos personalizados, as pastas e os arquivos serão preservados quando o Construtor de Relatórios for removido.</span><span class="sxs-lookup"><span data-stu-id="82fa2-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="82fa2-110">Apenas os arquivos do Construtor de Relatórios serão removidos.</span><span class="sxs-lookup"><span data-stu-id="82fa2-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="82fa2-111">Para desinstalar o Construtor de Relatórios a partir do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="82fa2-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="82fa2-112">No menu **Iniciar** , clique em **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="82fa2-113">No Painel de Controle, clique em **Programas e Recursos**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="82fa2-114">Localize o  Construtor de Relatórios na lista Nome e clique nele.</span><span class="sxs-lookup"><span data-stu-id="82fa2-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="82fa2-115">Clique em **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="82fa2-116">Se solicitado a confirmar a desinstalação do Construtor de Relatórios, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="82fa2-117">Para desinstalar o Construtor de Relatórios a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="82fa2-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="82fa2-118">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="82fa2-119">Na caixa de texto **abrir** , digite`cmd.`</span><span class="sxs-lookup"><span data-stu-id="82fa2-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="82fa2-120">Na janela do prompt de comando, navegue até pasta com ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="82fa2-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="82fa2-121">Digite uma linha de comando básica, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="82fa2-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="82fa2-122">Se você puder incluir o registro em log, use uma linha de comando como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="82fa2-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="82fa2-123">Pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fa2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82fa2-124">See Also</span></span>  
 <span data-ttu-id="82fa2-125">[Instalar, desinstalar e Construtor de Relatórios suporte](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="82fa2-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="82fa2-126">Instale a versão autônoma do Construtor de Relatórios &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="82fa2-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
