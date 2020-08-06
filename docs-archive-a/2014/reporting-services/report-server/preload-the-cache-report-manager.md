---
title: Pré-carregar o cache (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680819"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="b151f-102">Pré-carregar o cache (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="b151f-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="b151f-103">Você pode pré-carregar o cache para um conjunto de dados compartilhado criando um plano de atualização do cache para o conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b151f-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="b151f-104">Você pode pré-carregar o cache para um relatório de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="b151f-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="b151f-105">Criar um plano de atualização do cache para o relatório.</span><span class="sxs-lookup"><span data-stu-id="b151f-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="b151f-106">Este é o método preferencial.</span><span class="sxs-lookup"><span data-stu-id="b151f-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="b151f-107">Usar uma assinatura controlada por dados para pré-carregar o cache com instâncias de relatórios com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b151f-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="b151f-108">Essa era a única maneira de pré-carregar o cache em versões do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] anteriores ao [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b151f-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="b151f-109">Para obter mais informações, consulte [Armazenando relatórios em cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b151f-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="b151f-110">As condições a seguir devem ser atendidas para que seja possível armazenar em cache um relatório ou um conjunto de dados compartilhado:</span><span class="sxs-lookup"><span data-stu-id="b151f-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="b151f-111">O conjunto de dados compartilhado ou o relatório deve ter o armazenamento em cache habilitado.</span><span class="sxs-lookup"><span data-stu-id="b151f-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="b151f-112">As fontes de dados compartilhadas do conjunto de dados compartilhado ou do relatório devem estar configurados para usar credenciais armazenadas ou nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="b151f-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="b151f-113">O serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="b151f-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="b151f-114">Para pré-carregar o cache criando um plano de atualização do cache</span><span class="sxs-lookup"><span data-stu-id="b151f-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="b151f-115">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b151f-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b151f-116">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e navegue até o item que deseja armazenar em cache.</span><span class="sxs-lookup"><span data-stu-id="b151f-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="b151f-117">Focalize o item, clique na lista suspensa e clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="b151f-118">Clique na guia **Opções de Atualização do Cache** .</span><span class="sxs-lookup"><span data-stu-id="b151f-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="b151f-119">Na barra de ferramentas, clique em **Novo Plano de Atualização do Cache**.</span><span class="sxs-lookup"><span data-stu-id="b151f-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b151f-120">Se o item não tiver o armazenamento em cache habilitado, será solicitado que você habilite o armazenamento em cache.</span><span class="sxs-lookup"><span data-stu-id="b151f-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="b151f-121">Para habilitar o cache, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b151f-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="b151f-122">A página de Plano de Atualização do Cache é aberta.</span><span class="sxs-lookup"><span data-stu-id="b151f-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="b151f-123">Opcionalmente, digite uma descrição para o plano de atualização.</span><span class="sxs-lookup"><span data-stu-id="b151f-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="b151f-124">Para uma agenda compartilhada, clique em **Agenda Compartilhada**e selecione o nome da agenda a ser usada.</span><span class="sxs-lookup"><span data-stu-id="b151f-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="b151f-125">Para um agendamento personalizado, clique em **Agendamento específico do item**e clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b151f-126">Configurar o agendamento</span><span class="sxs-lookup"><span data-stu-id="b151f-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="b151f-127">Para pré-carregar o cache com um relatório específico ao usuário usando uma assinatura controlada por dados</span><span class="sxs-lookup"><span data-stu-id="b151f-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="b151f-128">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b151f-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b151f-129">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e navegue até o relatório para o qual você deseja criar uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="b151f-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="b151f-130">Clique no relatório, na guia **Assinaturas** e em **Nova Assinatura Controlada por Dados**.</span><span class="sxs-lookup"><span data-stu-id="b151f-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="b151f-131">Opcionalmente, digite uma descrição para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="b151f-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="b151f-132">Na lista **Especifique como os destinatários devem ser notificados** , selecione **Provedor de Entrega Nulo**.</span><span class="sxs-lookup"><span data-stu-id="b151f-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="b151f-133">Especifique um tipo de fonte de dados e clique em **Avançar** para configurar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b151f-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="b151f-134">Especifique o tipo de conexão, a cadeia de conexão e as credenciais para acessar a fonte de dados que contém dados de assinante.</span><span class="sxs-lookup"><span data-stu-id="b151f-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="b151f-135">O exemplo a seguir ilustra uma cadeia de conexão usada para se conectar a um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chamado Assinantes:</span><span class="sxs-lookup"><span data-stu-id="b151f-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="b151f-136">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="b151f-137">Especifique a consulta ou o comando que recupera dados de assinante.</span><span class="sxs-lookup"><span data-stu-id="b151f-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="b151f-138">Opcionalmente, aumente o período de tempo limite para as consultas que levam muito tempo para serem processadas.</span><span class="sxs-lookup"><span data-stu-id="b151f-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="b151f-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b151f-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="b151f-140">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-140">Click **Validate**.</span></span> <span data-ttu-id="b151f-141">A consulta deve ser validada antes de você continuar.</span><span class="sxs-lookup"><span data-stu-id="b151f-141">The query must be validated before you continue.</span></span> <span data-ttu-id="b151f-142">Quando a mensagem **Consulta validada com êxito** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="b151f-143">Como você não pode configurar as configurações de extensão de entrega para o provedor de entrega nulo, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="b151f-144">Especifique os valores de parâmetro do relatório para a assinatura e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="b151f-145">Especifique quando a assinatura é processada.</span><span class="sxs-lookup"><span data-stu-id="b151f-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="b151f-146">Não escolha **Quando os dados do relatório forem atualizados no servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="b151f-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="b151f-147">Essa definição se aplica somente a instantâneos.</span><span class="sxs-lookup"><span data-stu-id="b151f-147">That setting is for snapshots only.</span></span> <span data-ttu-id="b151f-148">Se quiser usar um agendamento preexistente, selecione **Em um agendamento compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="b151f-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="b151f-149">Ou, para criar uma agenda personalizada, clique em **Em um agendamento criado para esta assinatura** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="b151f-150">Configure a agenda e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b151f-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b151f-151">Para que os assinantes recebam o relatório mais recente, a gente que você configura deve ser consistente com a agenda de entrega do relatório definida para os assinantes.</span><span class="sxs-lookup"><span data-stu-id="b151f-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="b151f-152">Para obter mais informações, consulte [Gerenciador de Relatórios &#40;modo nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b151f-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="b151f-153">Configure as opções de Execução para o relatório como pode ser visto a seguir.</span><span class="sxs-lookup"><span data-stu-id="b151f-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="b151f-154">Na página de relatório, clique na guia **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="b151f-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="b151f-155">No quadro esquerdo, clique na guia **Execução** .</span><span class="sxs-lookup"><span data-stu-id="b151f-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="b151f-156">Na página, selecione **Processar esse relatório com os dados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="b151f-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="b151f-157">Escolha um das duas opções de cache a seguir e configure a validade do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="b151f-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="b151f-158">Para fazer com que uma cópia armazenada em cache expire depois de um período de tempo específico, clique em **Armazenar uma cópia temporária do relatório em cache. Expirar cópia de relatório após alguns minutos.**</span><span class="sxs-lookup"><span data-stu-id="b151f-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="b151f-159">Digite o número de minutos para a validade do relatório.</span><span class="sxs-lookup"><span data-stu-id="b151f-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="b151f-160">Para fazer com que a cópia armazenada em cache expire em um agendamento, clique em **Armazenar uma cópia temporária do relatório em cache. Expirar cópia de relatório no seguinte agendamento.**</span><span class="sxs-lookup"><span data-stu-id="b151f-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="b151f-161">Clique em **Configurar**ou selecione um agendamento compartilhado para definir um agendamento para a expiração do relatório.</span><span class="sxs-lookup"><span data-stu-id="b151f-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="b151f-162">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b151f-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b151f-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b151f-163">See Also</span></span>  
 <span data-ttu-id="b151f-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="b151f-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="b151f-165">[Criar uma assinatura controlada por dados &#40;Tutorial do SSRS&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b151f-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="b151f-166">[Desempenho, instantâneos, cache &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="b151f-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="b151f-167">[Definir propriedades de processamento de relatório](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b151f-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="b151f-168">Armazenando relatórios em cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b151f-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
