---
title: 'Lição 3: Definindo uma assinatura controlada por dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686096"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="7b441-102">Lesson 3: Defining a Data-Driven Subscription</span><span class="sxs-lookup"><span data-stu-id="7b441-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="7b441-103">Nesta lição, você vai usar as páginas da assinatura controlada por dados para se conectar a uma fonte de dados de assinatura, criar uma consulta que recupera dados de assinatura e mapear o conjunto de resultados para opções de relatório e entrega.</span><span class="sxs-lookup"><span data-stu-id="7b441-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b441-104">Antes de começar, verifique se o serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="7b441-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="7b441-105">Se não estiver, não será possível salvar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="7b441-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="7b441-106">Esta lição pressupõe que você concluiu a Lição 1 e Lição 2, e que a fonte de dados de relatório usa credenciais armazenadas.</span><span class="sxs-lookup"><span data-stu-id="7b441-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="7b441-107">Para obter mais informações, consulte [Lição 2: modificando as propriedades da fonte de dados do relatório](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span><span class="sxs-lookup"><span data-stu-id="7b441-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="7b441-108">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="7b441-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="7b441-109">Iniciar o assistente de assinatura controlada por dados</span><span class="sxs-lookup"><span data-stu-id="7b441-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="7b441-110">Etapa 1 - Definir uma descrição</span><span class="sxs-lookup"><span data-stu-id="7b441-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="7b441-111">Etapa 2 - Definir uma conexão com a fonte de dados de assinante</span><span class="sxs-lookup"><span data-stu-id="7b441-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="7b441-112">Etapa 3 - Definir uma consulta para recuperar dados de assinante</span><span class="sxs-lookup"><span data-stu-id="7b441-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="7b441-113">Etapa 4 - Definir opções de entrega</span><span class="sxs-lookup"><span data-stu-id="7b441-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="7b441-114">Etapa 5 - Configurar um valor de parâmetro para variar a saída de relatório</span><span class="sxs-lookup"><span data-stu-id="7b441-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="7b441-115">Etapa 6 - Para agendar uma assinatura</span><span class="sxs-lookup"><span data-stu-id="7b441-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="7b441-116">Iniciar o assistente de assinatura controlada por dados</span><span class="sxs-lookup"><span data-stu-id="7b441-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="7b441-117">No Gerenciador de Relatórios, clique em **Página Inicial**e navegue até a pasta que contém o relatório **Pedidos de Vendas** .</span><span class="sxs-lookup"><span data-stu-id="7b441-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="7b441-118">No menu de contexto do relatório, clique em **Gerenciar**e clique na guia **Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="7b441-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="7b441-119">Clique em **nova assinatura voltada para dados**.</span><span class="sxs-lookup"><span data-stu-id="7b441-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="7b441-120">Se este botão não estiver visível, você não tem permissões do Gerenciador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7b441-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="7b441-121">Etapa 1 – definir uma descrição</span><span class="sxs-lookup"><span data-stu-id="7b441-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="7b441-122">Digite **Entrega de ordem de venda** na descrição.</span><span class="sxs-lookup"><span data-stu-id="7b441-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="7b441-123">Selecione **Compartilhamento de Arquivos do Windows** para **Especifique como os destinatários devem ser notificados**.</span><span class="sxs-lookup"><span data-stu-id="7b441-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="7b441-124">Selecione **Especificar apenas para essa assinatura**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="7b441-125">Etapa 2 – definir uma conexão com a fonte de dados do assinante</span><span class="sxs-lookup"><span data-stu-id="7b441-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="7b441-126">Selecione **Microsoft SQL Server** como o tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7b441-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="7b441-127">Em Cadeia de conexão, digite a seguinte cadeia de conexão:</span><span class="sxs-lookup"><span data-stu-id="7b441-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b441-128">Os assinantes são o banco de dados que você criou na lição 1.</span><span class="sxs-lookup"><span data-stu-id="7b441-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="7b441-129">Clique em **Credenciais armazenadas com segurança no servidor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="7b441-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="7b441-130">Em **Nome de Usuário** e **Senha**, digite seu nome de usuário de domínio e senha.</span><span class="sxs-lookup"><span data-stu-id="7b441-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="7b441-131">Inclua a conta de domínio e de usuário ao especificar **Nome de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="7b441-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b441-132">As credenciais usadas para a conexão com uma fonte de dados de assinante não são retransmitidas para o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b441-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="7b441-133">Se você modificar a assinatura mais tarde, deverá digitar novamente a senha usada para a conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7b441-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="7b441-134">Selecione **Usar as credenciais do Windows ao conectar-se à fonte de dados**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="7b441-135">Etapa 3 – definir uma consulta para recuperar dados do assinante</span><span class="sxs-lookup"><span data-stu-id="7b441-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="7b441-136">Na caixa de consulta, digite a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="7b441-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="7b441-137">Especifique um tempo limite de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="7b441-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="7b441-138">Clique em **Validar**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="7b441-139">Etapa 4 – definir opções de entrega</span><span class="sxs-lookup"><span data-stu-id="7b441-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="7b441-140">Em **Nome de arquivo**, selecione **Obtenha o valor no banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b441-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="7b441-141">Selecione o campo **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="7b441-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="7b441-142">Para **Caminho**, selecione **Especifique um valor estático**.</span><span class="sxs-lookup"><span data-stu-id="7b441-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="7b441-143">Em Definindo Valor, digite o nome de um compartilhamento de arquivos públicos para os quais você tem permissões de gravação (por exemplo, `\\mycomputer\public\myreports`).</span><span class="sxs-lookup"><span data-stu-id="7b441-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="7b441-144">Em **Formato de Renderização**, selecione **Obtenha o valor no banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b441-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="7b441-145">Selecione **formato**.</span><span class="sxs-lookup"><span data-stu-id="7b441-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="7b441-146">Em **Modo de gravação**, selecione **Especifique um valor estático** e selecione **Incrementação automática**.</span><span class="sxs-lookup"><span data-stu-id="7b441-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="7b441-147">Em **Extensão de Arquivo**, selecione **Especifique um valor estático** e selecione **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="7b441-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="7b441-148">Em **Nome de usuário**, selecione **Especifique um valor estático**.</span><span class="sxs-lookup"><span data-stu-id="7b441-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="7b441-149">Digite sua conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="7b441-149">Type your domain user account.</span></span> <span data-ttu-id="7b441-150">Insira neste formato: `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="7b441-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="7b441-151">A conta de usuário precisa ter permissões para o caminho que você configurou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="7b441-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="7b441-152">Em **Senha**, selecione **Especifique um valor estático**.</span><span class="sxs-lookup"><span data-stu-id="7b441-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="7b441-153">Digite sua senha.</span><span class="sxs-lookup"><span data-stu-id="7b441-153">Type your password.</span></span> <span data-ttu-id="7b441-154">Digite a senha com cuidado.</span><span class="sxs-lookup"><span data-stu-id="7b441-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="7b441-155">O assistente não valida a senha.</span><span class="sxs-lookup"><span data-stu-id="7b441-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="7b441-156">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="7b441-157">Etapa 5 – configurar um valor de parâmetro para saída de relatório muito</span><span class="sxs-lookup"><span data-stu-id="7b441-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="7b441-158">Em **OrderNumber**, selecione **Obtenha o valor no banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b441-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="7b441-159">Em Valor, selecione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="7b441-159">In Value, select **Order**.</span></span> <span data-ttu-id="7b441-160">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="7b441-161">Etapa 6 – para agendar uma assinatura</span><span class="sxs-lookup"><span data-stu-id="7b441-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="7b441-162">Clique em **Em um agendamento criado para esta assinatura**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b441-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="7b441-163">Em **Detalhes do Agendamento**, clique em **Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="7b441-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="7b441-164">Especifique uma hora de início que esteja alguns minutos adiantados da hora atual.</span><span class="sxs-lookup"><span data-stu-id="7b441-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="7b441-165">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7b441-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b441-166">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7b441-166">Next Steps</span></span>  
 <span data-ttu-id="7b441-167">Quando a assinatura é executada, quatro arquivos de relatórios são entregues no compartilhamento de arquivos especificado, um para cada pedido na fonte de dados *Assinantes* .</span><span class="sxs-lookup"><span data-stu-id="7b441-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="7b441-168">Cada entrega deve ser exclusiva em termos de dados (os dados devem ser específicos do pedido), formato de renderização e formato de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7b441-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="7b441-169">Você pode abrir cada relatório da pasta compartilhada para verificar se cada versão está personalizada com base nas opções de assinatura definidas.</span><span class="sxs-lookup"><span data-stu-id="7b441-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="7b441-170">![Lista de arquivos criados pela assinatura](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Lista de arquivos criados pela assinatura")</span><span class="sxs-lookup"><span data-stu-id="7b441-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="7b441-171">A página de assinatura no Gerenciador de Relatórios conterá a data da **Última Execução** e o **Status** da assinatura.</span><span class="sxs-lookup"><span data-stu-id="7b441-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b441-172">Atualize a página depois que a assinatura for executada para consultar as informações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="7b441-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="7b441-173">![Resultados da assinatura no Gerenciador de Relatórios](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Resultados da assinatura no Gerenciador de Relatórios")</span><span class="sxs-lookup"><span data-stu-id="7b441-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="7b441-174">Esta etapa conclui o tutorial “Definindo uma assinatura controlada por dados”.</span><span class="sxs-lookup"><span data-stu-id="7b441-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="7b441-175">Para saber mais sobre outros [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutoriais, consulte [Reporting Services tutoriais &#40;&#41;do SSRS ](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7b441-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b441-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b441-176">See Also</span></span>  
 <span data-ttu-id="7b441-177">[Criar uma assinatura controlada por dados &#40;Tutorial do SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="7b441-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="7b441-178">[Assinaturas e entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7b441-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="7b441-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="7b441-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="7b441-180">[Criar, modificar e excluir uma assinatura controlada por dados](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="7b441-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="7b441-181">Usar uma fonte de dados externa para obter dados de assinante &#40;Assinatura controlada por dados&#41;</span><span class="sxs-lookup"><span data-stu-id="7b441-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
