---
title: Página de propriedades opções de instantâneo (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f6641f59-5267-4f57-8957-63b93d1a9679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3025b23dfe498a92c2ce1d8535229d8d23dfd429
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679122"
---
# <a name="snapshot-options-properties-page-report-manager"></a><span data-ttu-id="ae5ef-102">Página de propriedades Opções de Instantâneo (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="ae5ef-102">Snapshot Options Properties Page (Report Manager)</span></span>
  <span data-ttu-id="ae5ef-103">Use a página de propriedades Opções de Instantâneo para agendar instantâneos de relatório a serem adicionados ao histórico de relatórios e para definir limites do número de instantâneos de relatórios armazenados nesse histórico.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-103">Use the Snapshot Options properties page to schedule report snapshots to be added to report history, and to set limits on the number of report snapshots that are stored in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae5ef-104">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae5ef-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ae5ef-105">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consulte [serviços de banco de dados adicionais](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span><span class="sxs-lookup"><span data-stu-id="ae5ef-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Additional Database Services](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="ae5ef-106">Navegação</span><span class="sxs-lookup"><span data-stu-id="ae5ef-106">Navigation</span></span>  
 <span data-ttu-id="ae5ef-107">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-snapshot-options-properties-page-for-a-report"></a><span data-ttu-id="ae5ef-108">Para abrir a página de propriedades Opções de Instantâneo de um relatório</span><span class="sxs-lookup"><span data-stu-id="ae5ef-108">To open the Snapshot Options properties page for a report</span></span>  
  
1.  <span data-ttu-id="ae5ef-109">Abra o Gerenciador de Relatórios e localize o relatório cujas propriedades de instantâneo você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-109">Open Report Manager, and locate the report for which you want to configure report snapshot properties.</span></span>  
  
2.  <span data-ttu-id="ae5ef-110">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="ae5ef-111">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="ae5ef-112">Esse procedimento abre a página de propriedades Geral do relatório.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-112">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="ae5ef-113">Selecione a guia **Opções de Instantâneo** .</span><span class="sxs-lookup"><span data-stu-id="ae5ef-113">Select the **Snapshot Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae5ef-114">Opções</span><span class="sxs-lookup"><span data-stu-id="ae5ef-114">Options</span></span>  
 <span data-ttu-id="ae5ef-115">**Permitir a criação manual de histórico de relatórios**</span><span class="sxs-lookup"><span data-stu-id="ae5ef-115">**Allow report history to be created manually**</span></span>  
 <span data-ttu-id="ae5ef-116">Marque esta caixa de seleção para adicionar instantâneos ao histórico de relatório conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-116">Select this check box to add snapshots to report history as needed.</span></span> <span data-ttu-id="ae5ef-117">Marcando esta caixa de seleção, o botão **Novo Instantâneo** aparecerá na página Histórico.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-117">Selecting this check box causes the **New Snapshot** button to appear on the History page.</span></span>  
  
 <span data-ttu-id="ae5ef-118">**Armazene todos os instantâneos de execução de relatório no histórico de relatórios**</span><span class="sxs-lookup"><span data-stu-id="ae5ef-118">**Store all report execution snapshots in report history**</span></span>  
 <span data-ttu-id="ae5ef-119">Marque essa caixa de seleção para copiar um instantâneo de relatório gerado com base nas propriedades de execução de relatório no histórico do relatório.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-119">Select this check box to copy a report snapshot that you generate based on report execution properties to report history.</span></span> <span data-ttu-id="ae5ef-120">Você pode definir propriedades de execução de relatório para executar um relatório de um instantâneo gerado.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-120">You can set report execution properties to run a report from a generated snapshot.</span></span> <span data-ttu-id="ae5ef-121">Definindo essa propriedade de histórico de relatórios você pode manter um registro de todos os instantâneos gerados com o tempo, colocando cópias deles no histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-121">By setting this report history property, you can keep a record of all reports snapshots that are generated over time by placing copies of them in report history.</span></span>  
  
 <span data-ttu-id="ae5ef-122">**Use o agendamento a seguir para adicionar instantâneos ao histórico de relatórios**</span><span class="sxs-lookup"><span data-stu-id="ae5ef-122">**Use the following schedule to add snapshots to report history**</span></span>  
 <span data-ttu-id="ae5ef-123">Marque esta caixa de seleção para adicionar instantâneos ao histórico do relatório em uma base de agendamento.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-123">Select this check box to add snapshots to report history on a scheduled basis.</span></span> <span data-ttu-id="ae5ef-124">Você pode criar uma agenda usada exclusivamente para esse propósito ou pode selecionar uma agenda compartilhada predefinida se ela contiver as informações de agendamento necessárias.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-124">You can create a schedule that is used exclusively for this purpose, or you can select a predefined shared schedule if one contains the schedule information you want.</span></span>  
  
 <span data-ttu-id="ae5ef-125">**Selecione o número de instantâneos a serem mantidos**</span><span class="sxs-lookup"><span data-stu-id="ae5ef-125">**Select the number of snapshots to keep**</span></span>  
 <span data-ttu-id="ae5ef-126">Selecione das opções seguintes para controlar o número de relatórios mantido no histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-126">Select from the following options to control the number of reports that are kept in report history.</span></span> <span data-ttu-id="ae5ef-127">Configurações de histórico de relatórios podem variar para cada relatório.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-127">Report history settings can vary for each report.</span></span>  
  
-   <span data-ttu-id="ae5ef-128">Selecione **Usar configuração padrão** para reter a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-128">Select **Use default setting** to retain the default setting.</span></span> <span data-ttu-id="ae5ef-129">O administrador de servidor de relatórios controla uma configuração mestre para armazenamento de histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-129">The report server administrator controls a master setting for report history storage.</span></span> <span data-ttu-id="ae5ef-130">Se você escolher essa opção, o número de instantâneos retidos será obtido dessa configuração mestra.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-130">If you choose this option, the number of snapshots that are retained is obtained from this master setting.</span></span>  
  
-   <span data-ttu-id="ae5ef-131">Selecione **Mantenha um número ilimitado de instantâneos no histórico de relatório** para reter todos os instantâneos de histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-131">Select **Keep an unlimited number of snapshots in report history** to retain all report history snapshots.</span></span> <span data-ttu-id="ae5ef-132">Você deve excluir instantâneos manualmente para reduzir o tamanho de histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-132">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
-   <span data-ttu-id="ae5ef-133">Selecione **Limitar as cópias do histórico de relatório** para reter um número fixo de instantâneos.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-133">Select **Limit the copies of report history** to retain a set number of snapshots.</span></span> <span data-ttu-id="ae5ef-134">Quando o limite é alcançado, cópias mais antigas são removidas do histórico do relatório para liberar espaço para cópias mais atuais.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-134">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="ae5ef-135">O histórico de relatórios é armazenado no banco de dados do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-135">Report history is stored in the report server database.</span></span> <span data-ttu-id="ae5ef-136">Se você tiver grandes relatórios ou vários relatórios para os quais queira manter histórico, considere limitar a quantidade de histórico do relatório para ajudar a gerenciar os requisitos de espaço em disco do banco de dados do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-136">If you have large reports or numerous reports for which you want to maintain history, consider limiting the amount of report history to help manage the disk space requirements of the report server database.</span></span>  
  
 <span data-ttu-id="ae5ef-137">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="ae5ef-137">**Apply**</span></span>  
 <span data-ttu-id="ae5ef-138">Clique para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="ae5ef-138">Click to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5ef-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae5ef-139">See Also</span></span>  
 <span data-ttu-id="ae5ef-140">[Adicionar um instantâneo ao histórico de relatório &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ae5ef-140">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="ae5ef-141">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ae5ef-141">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="ae5ef-142">[Criar, modificar e excluir instantâneos no histórico de relatório](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span><span class="sxs-lookup"><span data-stu-id="ae5ef-142">[Create, Modify, and Delete Snapshots in Report History](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span></span>  
 [<span data-ttu-id="ae5ef-143">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="ae5ef-143">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
