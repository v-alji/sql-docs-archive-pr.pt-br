---
title: Criar um alerta de dados no Designer de Alertas de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682177"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="c78a2-102">Criar um Alerta de Dados no Designer de Alertas de Dados</span><span class="sxs-lookup"><span data-stu-id="c78a2-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="c78a2-103">Você cria definições de alerta de dados no Designer de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="c78a2-104">Depois de salvar as definições de alertas, é possível abri-la novamente, editá-la e salvá-la novamente no Designer de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="c78a2-105">Para obter informações sobre como editar definições de alertas, consulte [Gerenciar meus alertas de dados no Gerenciador de Alertas de Dados](manage-my-data-alerts-in-data-alert-manager.md) e [Editar um alerta de dados no Designer de Alertas](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c78a2-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="c78a2-106">Para criar uma definição de alerta de dados</span><span class="sxs-lookup"><span data-stu-id="c78a2-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="c78a2-107">Localize a biblioteca do SharePoint que contém o relatório para o qual você deseja criar uma definição de alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="c78a2-108">Clique no relatório.</span><span class="sxs-lookup"><span data-stu-id="c78a2-108">Click the report.</span></span>

     <span data-ttu-id="c78a2-109">O relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="c78a2-109">The report runs.</span></span> <span data-ttu-id="c78a2-110">Se o relatório for parametrizado, verifique se o relatório mostra os dados sobre os quais você deseja receber mensagens de alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="c78a2-111">Se você não vir as colunas ou valores nos quais está interessado, talvez seja necessário executar o relatório novamente, com o uso de valores de parâmetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="c78a2-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c78a2-112">Os valores de parâmetros que você escolheu para executar o relatório são salvos na definição de alerta e serão usados quando o relatório for executado novamente como uma etapa do processamento da definição de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="c78a2-113">Para usar diferentes valores de parâmetro, você deve criar uma nova definição de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="c78a2-114">No menu **Ações** , clique em **Novo Alerta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="c78a2-115">A imagem a seguir mostra o menu **Ações** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="c78a2-116">![Abra o Designer de Alertas da biblioteca do SharePoint](media/rs-openalertdesigneriw.gif "Abra o Designer de Alertas da biblioteca do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="c78a2-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="c78a2-117">O Designer de Alertas de Dados é aberto e mostra as primeiras 100 linhas do primeiro feed de dados que o relatório gera em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="c78a2-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c78a2-118">Se você não visualizar a opção **Novo Alerta de Dados** , o serviço de alerta não está configurado no site do SharePoint ou a edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não inclui alertas de dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="c78a2-119">Para obter mais informações, consulte [Serviço SharePoint do Reporting Services e aplicativos de serviço](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="c78a2-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="c78a2-120">Se a opção **Novo Alerta de Dados** estiver acinzentada, a fonte de dados de relatório está configurada para usar credenciais de segurança integradas ou para solicitar credenciais.</span><span class="sxs-lookup"><span data-stu-id="c78a2-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="c78a2-121">Para tornar a opção **Novo Alerta de Dados** disponível, você deve atualizar a fonte de dados para usar credenciais armazenadas ou nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="c78a2-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="c78a2-122">O nome do feed de dados é exibido na lista suspensa **Nome de dados do relatório** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="c78a2-123">Opcionalmente, selecione um feed de dados diferente na lista suspensa **Nome de dados do relatório** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="c78a2-124">Se nenhum feed de dados for gerado a partir do relatório, você não poderá criar uma definição de alerta para o relatório.</span><span class="sxs-lookup"><span data-stu-id="c78a2-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="c78a2-125">O layout do relatório determina o conteúdo de cada feed de dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="c78a2-126">Para obter mais informações, consulte [Gerando feeds de dados de relatórios &#40;Construtor de Relatórios e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c78a2-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="c78a2-127">Opcionalmente, na caixa de texto **Nome do alerta** , atualize o nome padrão para que seja mais significativo.</span><span class="sxs-lookup"><span data-stu-id="c78a2-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="c78a2-128">O nome padrão da definição de alerta é o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="c78a2-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="c78a2-129">Os nomes de definições de alertas não precisam ser exclusivos, o que pode dificultar sua diferenciação quando você exibir a lista de alertas mais tarde no Gerenciador de Alertas de Dados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="c78a2-130">É recomendável usar nomes de definições de alertas significativos e exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c78a2-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="c78a2-131">Opcionalmente, altere a opção de dados padrão de **quaisquer dados do feed de dados tem** para **nenhum dado do feed de dados tem**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="c78a2-132">Clique em **Adicionar regra**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-132">Click **Add rule**.</span></span>

     <span data-ttu-id="c78a2-133">Uma lista das colunas no feed de dados é exibida.</span><span class="sxs-lookup"><span data-stu-id="c78a2-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="c78a2-134">Na lista, selecione a coluna que você deseja usar na regra e selecione um operador de comparação e insira o valor de limite.</span><span class="sxs-lookup"><span data-stu-id="c78a2-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="c78a2-135">Dependendo do tipo dos dados da coluna selecionada, diferentes operadores de comparação serão listados.</span><span class="sxs-lookup"><span data-stu-id="c78a2-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="c78a2-136">Se a coluna tiver um tipo de dados de data, um ícone de calendário será exibido ao lado do valor de limite da regra.</span><span class="sxs-lookup"><span data-stu-id="c78a2-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="c78a2-137">É possível inserir dados com um clique em uma data no calendário ou por meio de digitação da data.</span><span class="sxs-lookup"><span data-stu-id="c78a2-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="c78a2-138">O Designer de Alertas de Dados fornece dois modos de comparação: **Modo de Entrada de Valor** e **Modo de Seleção de Campo**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="c78a2-139">O padrão é **Modo de Entrada de Valor**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="c78a2-140">Você só pode adicionar cláusulas OR quando está no **Modo de Entrada de Valor** e está usando a comparação **is** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="c78a2-141">Para adicionar uma cláusula OR, clique na seta para baixo e clique em **Modo de Entrada de Valor**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="c78a2-142">Digite o valor de comparação.</span><span class="sxs-lookup"><span data-stu-id="c78a2-142">Type the comparison value.</span></span>

11. <span data-ttu-id="c78a2-143">Opcionalmente, clique nas reticências **(...)** novamente.</span><span class="sxs-lookup"><span data-stu-id="c78a2-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="c78a2-144">As reticências **(...)** aparecem na linha que contém a primeira cláusula.</span><span class="sxs-lookup"><span data-stu-id="c78a2-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="c78a2-145">Uma cláusula OR é adicionada sob e na regra AND.</span><span class="sxs-lookup"><span data-stu-id="c78a2-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="c78a2-146">Opcionalmente, clique na seta para baixo, selecione **Modo de Seleção de Campo**e selecione uma coluna na lista.</span><span class="sxs-lookup"><span data-stu-id="c78a2-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="c78a2-147">Você observará que as reticências **(...)** em que você clica para adicionar cláusulas ou foram desaparecedas.</span><span class="sxs-lookup"><span data-stu-id="c78a2-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="c78a2-148">Opcionalmente, clique em **Adicionar regra** novamente para adicionar mais regras.</span><span class="sxs-lookup"><span data-stu-id="c78a2-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="c78a2-149">As regras são combinadas com o uso do operador lógico AND.</span><span class="sxs-lookup"><span data-stu-id="c78a2-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="c78a2-150">Selecione uma opção na lista de recorrência.</span><span class="sxs-lookup"><span data-stu-id="c78a2-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="c78a2-151">Dependendo do tipo de recorrência, insira um intervalo.</span><span class="sxs-lookup"><span data-stu-id="c78a2-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="c78a2-152">Opcionalmente, clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="c78a2-153">Opcionalmente, altere a data de início da mensagem de alerta por meio da digitação de uma data diferente ou por maio da abertura do calendário e um clique em uma data do calendário.</span><span class="sxs-lookup"><span data-stu-id="c78a2-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="c78a2-154">A data inicial padrão é a data atual.</span><span class="sxs-lookup"><span data-stu-id="c78a2-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="c78a2-155">Opcionalmente, marque a caixa de seleção localizada ao lado de **Parar alerta em**e escolha uma data para parar a mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="c78a2-156">Por padrão, uma mensagem de alerta não tem nenhuma data de parada.</span><span class="sxs-lookup"><span data-stu-id="c78a2-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c78a2-157">Parar uma mensagem de alerta não exclui a definição do alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="c78a2-158">Depois que você parar uma mensagem de alerta, poderá reiniciá-la atualizando as datas de início e término.</span><span class="sxs-lookup"><span data-stu-id="c78a2-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="c78a2-159">Para obter informações sobre como excluir definições de alertas, consulte [Gerenciar meus alertas de dados no Gerenciador de Alertas de Dados](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c78a2-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="c78a2-160">Opcionalmente, desmarque a caixa de seleção **Enviar mensagens somente se os resultados forem alterados** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="c78a2-161">Se você enviar mensagens de alerta frequentemente, informações redundantes talvez não sejam bem-vindas e essa caixa de seleção deverá ser desmarcada.</span><span class="sxs-lookup"><span data-stu-id="c78a2-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="c78a2-162">Digite os endereços de email dos destinatários da mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="c78a2-163">Separe os endereços com ponto-e-vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c78a2-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="c78a2-164">Se o endereço de email da pessoa que criou a definição de alerta estiver disponível, ele será adicionado à caixa **Destinatário(s)** .</span><span class="sxs-lookup"><span data-stu-id="c78a2-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="c78a2-165">Opcionalmente, na caixa de texto **Assunto** , atualize a linha de Assunto da mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="c78a2-166">O assunto padrão é \*\*alerta de dados \<data alert name> para \*\*.</span><span class="sxs-lookup"><span data-stu-id="c78a2-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="c78a2-167">Opcionalmente, na caixa de texto **Descrição** , digite uma descrição da mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="c78a2-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="c78a2-168">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c78a2-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c78a2-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c78a2-169">See Also</span></span>
 <span data-ttu-id="c78a2-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Gerenciador de alertas de dados do designer de alertas de dados para administradores de](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) alertas [Reporting Services alertas de dados](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c78a2-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


