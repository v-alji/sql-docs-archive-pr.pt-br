---
title: Página Histórico de relatórios (Report Manager) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573648"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="302b4-102">Página Histórico de Relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="302b4-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="302b4-103">Use a página Histórico de Relatório para exibir instantâneos de relatório que são gerados e armazenados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="302b4-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="302b4-104">Dependendo das opções definidas no servidor de relatório, o histórico do relatórios poderá conter somente os instantâneos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="302b4-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="302b4-105">O histórico de relatório é sempre exibido no contexto do relatório de origem.</span><span class="sxs-lookup"><span data-stu-id="302b4-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="302b4-106">Você não pode exibir o histórico de todos os relatórios em um servidor de relatórios em um único lugar.</span><span class="sxs-lookup"><span data-stu-id="302b4-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="302b4-107">Para gerar histórico de relatórios, o relatório deve ser executado de modo autônomo (ou seja, ele deve usar credenciais armazenadas; relatórios com parâmetros devem conter valores de parâmetro padrão para todos os parâmetros).</span><span class="sxs-lookup"><span data-stu-id="302b4-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="302b4-108">Histórico de Relatórios pode ser gerado manualmente ou como uma operação agendada.</span><span class="sxs-lookup"><span data-stu-id="302b4-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="302b4-109">As propriedades de histórico no relatório determinam os modos pelos quais o histórico do relatório pode ser criado.</span><span class="sxs-lookup"><span data-stu-id="302b4-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="302b4-110">Você pode clicar em um instantâneo de histórico de relatórios para exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="302b4-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="302b4-111">Instantâneos exibidos em histórico de relatórios só são diferenciados pela data e hora em que foram criados.</span><span class="sxs-lookup"><span data-stu-id="302b4-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="302b4-112">Não existe indicação visual para distinguir se um relatório foi gerado em resposta a uma operação programada ou manual.</span><span class="sxs-lookup"><span data-stu-id="302b4-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="302b4-113">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302b4-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="302b4-114">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="302b4-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="302b4-115">Navegação</span><span class="sxs-lookup"><span data-stu-id="302b4-115">Navigation</span></span>  
 <span data-ttu-id="302b4-116">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="302b4-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="302b4-117">Para abrir a página Histórico de Relatórios</span><span class="sxs-lookup"><span data-stu-id="302b4-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="302b4-118">Abra o Gerenciador de Relatórios e localize o relatório cujos instantâneos você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="302b4-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="302b4-119">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="302b4-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="302b4-120">No menu suspenso, clique em **Exibir Histórico de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="302b4-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="302b4-121">Opções</span><span class="sxs-lookup"><span data-stu-id="302b4-121">Options</span></span>  
 <span data-ttu-id="302b4-122">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="302b4-122">**Delete**</span></span>  
 <span data-ttu-id="302b4-123">Clique para excluir um ou mais instantâneos.</span><span class="sxs-lookup"><span data-stu-id="302b4-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="302b4-124">Antes de clicar em **Excluir**, marque a caixa de seleção ao lado do instantâneo que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="302b4-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="302b4-125">**Novo Instantâneo**</span><span class="sxs-lookup"><span data-stu-id="302b4-125">**New Snapshot**</span></span>  
 <span data-ttu-id="302b4-126">Clique para adicionar um instantâneo a um histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="302b4-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="302b4-127">Esse botão é disponibilizado quando você escolhe a opção **Permitir que o histórico seja criado manualmente** na página de propriedades do Histórico do relatório.</span><span class="sxs-lookup"><span data-stu-id="302b4-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="302b4-128">**Última Execução**</span><span class="sxs-lookup"><span data-stu-id="302b4-128">**Last Run**</span></span>  
 <span data-ttu-id="302b4-129">Exibe a data e a hora em que o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="302b4-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="302b4-130">Clique em uma descrição para exibir um instantâneo específico.</span><span class="sxs-lookup"><span data-stu-id="302b4-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="302b4-131">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="302b4-131">**Size**</span></span>  
 <span data-ttu-id="302b4-132">Exibe o tamanho da definição do relatório mais os dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="302b4-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="302b4-133">Esse valor indica quanto espaço no banco de dados do servidor de relatórios é usado pela definição e dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="302b4-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="302b4-134">O tamanho do relatório renderizado, que inclui formatação, é maior, na verdade.</span><span class="sxs-lookup"><span data-stu-id="302b4-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="302b4-135">O tamanho total, indicado entre parênteses, é igual à soma de todos os instantâneos no histórico de relatório para o relatório atual.</span><span class="sxs-lookup"><span data-stu-id="302b4-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302b4-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="302b4-136">See Also</span></span>  
 <span data-ttu-id="302b4-137">[Exibir ou excluir o histórico de relatórios &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="302b4-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="302b4-138">[Adicionar um instantâneo ao histórico de relatório &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="302b4-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="302b4-139">[Página Propriedades gerais, relatórios &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="302b4-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="302b4-140">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="302b4-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="302b4-141">Página Propriedades de opções de instantâneo &#40;Report Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="302b4-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)