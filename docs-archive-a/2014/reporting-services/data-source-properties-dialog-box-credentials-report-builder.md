---
title: Caixa de diálogo Propriedades da fonte de dados, credenciais (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10017"
ms.assetid: 4531f09f-d653-4c05-a120-d7788838bc99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e47ba571e2b0adf2738499c1d027a4edde86e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575640"
---
# <a name="data-source-properties-dialog-box-credentials-report-builder"></a><span data-ttu-id="83d3b-102">Caixa de diálogo Propriedades da Fonte de Dados, Credenciais (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="83d3b-102">Data Source Properties Dialog Box, Credentials (Report Builder)</span></span>
  <span data-ttu-id="83d3b-103">Selecione **Credenciais** na caixa de diálogo **Propriedades da Fonte de Dados** para exibir e modificar as credenciais a fim de estabelecer conexão com uma fonte de dados inserida do relatório.</span><span class="sxs-lookup"><span data-stu-id="83d3b-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to an embedded data source in the report.</span></span> <span data-ttu-id="83d3b-104">As credenciais fornecidas são usadas para acessar a fonte de dados para externas para a visualização de relatórios.</span><span class="sxs-lookup"><span data-stu-id="83d3b-104">The credentials that you provide are used to access the data source for previewing reports.</span></span> <span data-ttu-id="83d3b-105">Para obter mais informações sobre credenciais, consulte [Especificar as credenciais no Construtor de Relatórios](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="83d3b-105">For more information about credentials, see [Specify Credentials in Report Builder](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83d3b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="83d3b-106">Options</span></span>  
 <span data-ttu-id="83d3b-107">**Usar a Autenticação do Windows (segurança integrada)**</span><span class="sxs-lookup"><span data-stu-id="83d3b-107">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="83d3b-108">Selecione esta opção para usar a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="83d3b-108">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="83d3b-109">**Usar este nome de usuário e senha**</span><span class="sxs-lookup"><span data-stu-id="83d3b-109">**Use this user name and password**</span></span>  
 <span data-ttu-id="83d3b-110">Selecione esta opção para fornecer um nome de usuário e senha específicos.</span><span class="sxs-lookup"><span data-stu-id="83d3b-110">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="83d3b-111">Em fontes de dados inseridas: quando você publicar o projeto do servidor de relatório no servidor de destino, o nome de usuário e a senha serão salvos como as credenciais armazenadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="83d3b-111">For embedded data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="83d3b-112">Para usar o nome de usuário e a senha como credenciais do Windows, é possível alterar as propriedades da fonte de dados compartilhada no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="83d3b-112">If you want to use the user name and password as Windows credentials, you can change the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="83d3b-113">Para obter mais informações, consulte [Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Gerenciador de Relatórios&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) na documentação do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="83d3b-113">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
 <span data-ttu-id="83d3b-114">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="83d3b-114">**User name**</span></span>  
 <span data-ttu-id="83d3b-115">Digite um nome de usuário para fazer logon na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="83d3b-115">Type a user name to log on to the data source.</span></span>  
  
 <span data-ttu-id="83d3b-116">**Senha**</span><span class="sxs-lookup"><span data-stu-id="83d3b-116">**Password**</span></span>  
 <span data-ttu-id="83d3b-117">Digite uma senha para fazer logon na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="83d3b-117">Type a password to log on to the data source.</span></span>  
  
 <span data-ttu-id="83d3b-118">**Solicitar credenciais**</span><span class="sxs-lookup"><span data-stu-id="83d3b-118">**Prompt for credentials**</span></span>  
 <span data-ttu-id="83d3b-119">Selecione esta opção para solicitar as credenciais quando o relatório for executado.</span><span class="sxs-lookup"><span data-stu-id="83d3b-119">Select this option to prompt for credentials when the report runs.</span></span>  
  
 <span data-ttu-id="83d3b-120">**Informar a cadeia de caracteres da solicitação**</span><span class="sxs-lookup"><span data-stu-id="83d3b-120">**Enter prompt string**</span></span>  
 <span data-ttu-id="83d3b-121">Digite uma instrução para que o usuário forneça as credenciais de logon para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="83d3b-121">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="83d3b-122">**Sem credenciais**</span><span class="sxs-lookup"><span data-stu-id="83d3b-122">**No credentials**</span></span>  
 <span data-ttu-id="83d3b-123">Selecione esta opção para não fornecer nenhuma credencial para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="83d3b-123">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="83d3b-124">Esta opção só funcionará se a fonte de dados não aceitar credenciais ou se você estiver passando as credenciais de alguma outra forma.</span><span class="sxs-lookup"><span data-stu-id="83d3b-124">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
 <span data-ttu-id="83d3b-125">Em algumas extensões de dados, a conta de execução autônoma deve estar configurada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="83d3b-125">From some data extensions, the unattended execution account must be configured on the report server.</span></span>  
  
 <span data-ttu-id="83d3b-126">Para obter mais informações, consulte o tópico sobre o tipo de fonte de dados correspondente em [Adicionar dados de fontes de dados externas &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) e [Configurar a conta de execução autônoma &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) na documentação do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="83d3b-126">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d3b-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83d3b-127">See Also</span></span>  
 <span data-ttu-id="83d3b-128">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="83d3b-128">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="83d3b-129">[Caixa de diálogo Propriedades da fonte de dados, Construtor de Relatórios geral &#40;&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="83d3b-129">[Data Source Properties Dialog Box, General &#40;Report Builder&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span></span>  
 <span data-ttu-id="83d3b-130">[Adicionar e verificar uma conexão de dados ou uma fonte de dados &#40;Construtor de Relatórios e SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="83d3b-130">[Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="83d3b-131">Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="83d3b-131">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
