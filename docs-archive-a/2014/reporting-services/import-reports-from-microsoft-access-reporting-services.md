---
title: Importar relatórios do Microsoft Access (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581699"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="38f17-102">Importar relatórios do Microsoft Access (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="38f17-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="38f17-103">No Report Designer, você pode importar relatórios de um [!INCLUDE[msCoName](../includes/msconame-md.md)] banco de dados ou projeto do Access.</span><span class="sxs-lookup"><span data-stu-id="38f17-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="38f17-104">O Access 2002 ou uma versão posterior deve estar instalado no mesmo computador no qual o Designer de Relatórios está instalado.</span><span class="sxs-lookup"><span data-stu-id="38f17-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="38f17-105">Quando você usar o recurso de importação, todos os relatórios no arquivo de banco de dados ou de projeto serão importados.</span><span class="sxs-lookup"><span data-stu-id="38f17-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="38f17-106">Se o seu arquivo do Access contiver muitos relatórios, é possível criar um projeto de relatório separado, para o qual importar os relatórios, e abrir os arquivos RDL individuais no projeto de relatório principal.</span><span class="sxs-lookup"><span data-stu-id="38f17-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="38f17-107">É possível editar os relatórios depois de importá-los para o Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f17-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38f17-108">O [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] não oferece suporte a todos os objetos de relatório do Access.</span><span class="sxs-lookup"><span data-stu-id="38f17-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not support all Access report objects.</span></span> <span data-ttu-id="38f17-109">Os itens que não são convertidos são exibidos na janela **lista de tarefas** .</span><span class="sxs-lookup"><span data-stu-id="38f17-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="38f17-110">Para obter mais informações, consulte [recursos de relatório de acesso com suporte &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38f17-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="38f17-111">Para importar relatórios do Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="38f17-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="38f17-112">Abra ou crie um projeto no qual devem ser importados os relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f17-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="38f17-113">No menu **projeto** , aponte para **importar relatórios**e clique em **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="38f17-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="38f17-114">Como alternativa, clique com o botão direito do mouse no projeto no Gerenciador de Soluções, aponte para **importar relatórios**e clique em **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="38f17-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="38f17-115">Na caixa de diálogo **abrir** , selecione o banco de dados do Access (. mdb,. accdb) ou o projeto (. adp) que contém os relatórios e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="38f17-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="38f17-116">Todos os relatórios no banco de dados ou arquivo de projeto são importados e listados na pasta Relatórios do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="38f17-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="38f17-117">Verifique a janela de **lista de tarefas** em busca de erros de compilação.</span><span class="sxs-lookup"><span data-stu-id="38f17-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="38f17-118">Para exibir a janela **lista de tarefas** , abra o menu **Exibir** , aponte para **outras janelas**e clique em **lista de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="38f17-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f17-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38f17-119">See Also</span></span>  
 [<span data-ttu-id="38f17-120">Criar relatórios com o Designer de Relatórios &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f17-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
