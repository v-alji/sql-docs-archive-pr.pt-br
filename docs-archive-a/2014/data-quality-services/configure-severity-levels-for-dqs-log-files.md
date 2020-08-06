---
title: Configurar níveis de gravidade para arquivos de log do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.log.f1
helpviewer_keywords:
- severity levels
- log files,severity levels
- dqs log files,severity levels
- logging,severity levels
- configure severity levels
ms.assetid: 66ffcdec-4bf7-4dd5-a221-fd9baefeeef4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 46fb9de1fbe1e3e59b20bb2ac7afeebe19ba2da5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678981"
---
# <a name="configure-severity-levels-for-dqs-log-files"></a><span data-ttu-id="f7c85-102">Configurar níveis de severidade para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="f7c85-102">Configure Severity Levels for DQS Log Files</span></span>
  <span data-ttu-id="f7c85-103">Este tópico descreve como configurar níveis de severidade para várias atividades e módulos no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) usando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7c85-103">This topic describes how to configure severity levels for various activities and modules in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="f7c85-104">Níveis de severidade definem a intensidade de eventos que ocorrem no DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c85-104">Severity levels define the intensity of events that occur in DQS.</span></span> <span data-ttu-id="f7c85-105">Eventos DQS têm os seguintes níveis de severidade, na ordem decrescente de severidade:</span><span class="sxs-lookup"><span data-stu-id="f7c85-105">DQS events have the following severity levels, in the decreasing order of severity:</span></span>  
  
-   <span data-ttu-id="f7c85-106">**Fatal**: erros críticos em runtime que podem causar resultados severos/inesperados.</span><span class="sxs-lookup"><span data-stu-id="f7c85-106">**Fatal**: Critical runtime errors that might cause severe/unexpected results.</span></span>  
  
-   <span data-ttu-id="f7c85-107">**Erro**: outros erros em runtime.</span><span class="sxs-lookup"><span data-stu-id="f7c85-107">**Error**: Other runtime errors.</span></span>  
  
-   <span data-ttu-id="f7c85-108">**Aviso**: avisos sobre eventos que podem resultar em um erro.</span><span class="sxs-lookup"><span data-stu-id="f7c85-108">**Warn**: Warning about events that might result in an error.</span></span>  
  
-   <span data-ttu-id="f7c85-109">**Informações**: informações sobre eventos em geral que não são um erro ou um aviso.</span><span class="sxs-lookup"><span data-stu-id="f7c85-109">**Info**: Information about general events that is not an error or a warning.</span></span> <span data-ttu-id="f7c85-110">Por exemplo, um processo de DQS foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="f7c85-110">For example, a DQS process has started.</span></span>  
  
-   <span data-ttu-id="f7c85-111">**Depuração**: informações detalhadas (detalhado) sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="f7c85-111">**Debug**: Detailed (verbose) information about the event.</span></span>  
  
 <span data-ttu-id="f7c85-112">Ao configurar níveis de severidade para várias atividades e módulos do DQS, você está filtrando as informações a serem registradas e gravando no arquivo de log do DQS para a respectiva atividade ou módulo do DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c85-112">By configuring severity levels for various DQS activities and modules, you are filtering the information that you want to be logged, and written to the DQS log file for the respective DQS activity or module.</span></span> <span data-ttu-id="f7c85-113">Por exemplo, se você definir o nível de severidade de uma atividade do DQS como **Aviso**, apenas as mensagens de aviso e severidade mais alta (Erro e Fatal) associadas com a atividade do DQS serão registradas.</span><span class="sxs-lookup"><span data-stu-id="f7c85-113">For example, if you set the severity level of a DQS activity to **Warn**, only warning and higher severity messages (Error and Fatal) associated with the DQS activity will be logged.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f7c85-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f7c85-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f7c85-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="f7c85-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f7c85-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="f7c85-116">Permissions</span></span>  
 <span data-ttu-id="f7c85-117">É necessário ter a função dqs_administrator no banco de dados DQS_MAIN para configurar definições de severidade de log.</span><span class="sxs-lookup"><span data-stu-id="f7c85-117">You must have the dqs_administrator role on the DQS_MAIN database to configure log severity settings.</span></span>  
  
##  <a name="configure-severity-levels-at-activity-level"></a><a name="ConfigureActivity"></a><span data-ttu-id="f7c85-118">Configurar níveis de severidade no nível de atividade</span><span class="sxs-lookup"><span data-stu-id="f7c85-118">Configure Severity Levels at Activity Level</span></span>  
 <span data-ttu-id="f7c85-119">Você pode definir configurações de severidade de log para as seguintes atividades no DQS: gerenciamento de domínio, descoberta de conhecimento, política de correspondência, limpeza de dados, correspondência de dados e serviços de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="f7c85-119">You can configure log severity settings for the following activities in DQS: domain management, knowledge discovery, matching policy, data cleansing, data matching, and reference data services.</span></span> <span data-ttu-id="f7c85-120">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="f7c85-120">To do so:</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="f7c85-121">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="f7c85-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="f7c85-122">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="f7c85-123">Em seguida, clique na guia **configurações de log** . As seguintes atividades do DQS são listadas para as quais você pode selecionar um nível de severidade: **Gerenciamento de domínio**, **descoberta de conhecimento**, **projeto de limpeza (ex. RDS)**, **política de correspondência e projeto de correspondência**e **RDS**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-123">Next, click the **Log Settings** tab. The following DQS activities are listed for which you can select a severity level: **Domain Management**, **Knowledge Discovery**, **Cleansing Project (Ex. RDS)**, **Matching Policy and Matching Project**, and **RDS**.</span></span>  
  
4.  <span data-ttu-id="f7c85-124">Para obter uma atividade do DQS, selecione o nível de severidade a ser registrado.</span><span class="sxs-lookup"><span data-stu-id="f7c85-124">For a DQS activity, select the severity level that you want to be logged.</span></span> <span data-ttu-id="f7c85-125">Você pode selecionar uma destas opções: **Fatal**, **Erro**, **Aviso**, **Informações**e **Depuração**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-125">You can select one among the following: **Fatal**, **Error**, **Warn**, **Info**, and **Debug**.</span></span> <span data-ttu-id="f7c85-126">Por exemplo, se você deseja que apenas mensagens fatais sejam gravadas nos arquivos de log do DQS para a atividade de descoberta de base de dados de conhecimento, selecione **Fatal** na lista suspensa na atividade **Descoberta da Base de Dados de Conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="f7c85-126">For example, if you want only fatal messages to be written to the DQS log files for the knowledge discovery activity, select **Fatal** in the drop-down list against the **Knowledge Discovery** activity.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7c85-127">Por padrão, **Erro** é selecionado para cada uma das atividades.</span><span class="sxs-lookup"><span data-stu-id="f7c85-127">By default, **Error** is selected for each of the activities.</span></span> <span data-ttu-id="f7c85-128">Isso implica que mensagens de erro e fatais sejam gravadas nos arquivos de log do DQS para cada atividade, por padrão.</span><span class="sxs-lookup"><span data-stu-id="f7c85-128">This implies that error and fatal messages will be written to the DQS log files for each activity, by default.</span></span>  
  
5.  <span data-ttu-id="f7c85-129">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-129">Click **Close**.</span></span>  
  
##  <a name="configure-severity-levels-at-module-level-advanced"></a><a name="ConfigureModule"></a><span data-ttu-id="f7c85-130">Configurar níveis de severidade no nível do módulo (avançado)</span><span class="sxs-lookup"><span data-stu-id="f7c85-130">Configure Severity Levels at Module Level (Advanced)</span></span>  
 <span data-ttu-id="f7c85-131">A seção **Avançado** na guia **Configurações de Log** permite que você defina configurações de severidade de log em um nível de módulo.</span><span class="sxs-lookup"><span data-stu-id="f7c85-131">The **Advanced** section in the **Log Settings** tab enables you to configure log severity settings at a module level.</span></span> <span data-ttu-id="f7c85-132">Módulos são assemblies do sistema DQS que implementam várias funcionalidades em um recurso no DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c85-132">Modules are DQS system assemblies that implement various functionalities within a feature in DQS.</span></span> <span data-ttu-id="f7c85-133">Por exemplo, a atividade de gerenciamento de domínio contém várias funcionalidades, como a definição de regras de domínio, a definição de condições de regra, a definição de regras do domínio cruzado para domínios compostos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f7c85-133">For example, the domain management activity contains various functionalities such as defining domain rules, defining rule conditions, defining cross-domain rules for composite domains, and so on.</span></span>  
  
 <span data-ttu-id="f7c85-134">Às vezes, o nível de granularidade no nível de atividade não é suficiente.</span><span class="sxs-lookup"><span data-stu-id="f7c85-134">At times, the granularity level at the activity level is not sufficient.</span></span> <span data-ttu-id="f7c85-135">Talvez você queira investigar um problema que está ocorrendo em um módulo específico de uma atividade.</span><span class="sxs-lookup"><span data-stu-id="f7c85-135">You might want to investigate an issue that is occurring in a particular module within an activity.</span></span> <span data-ttu-id="f7c85-136">Convém ter uma opção para configurar severidade de log no nível de módulo para isolar e controlar o problema com mais precisão.</span><span class="sxs-lookup"><span data-stu-id="f7c85-136">It helps to have an option to configure log severities at the module level to isolate and track the issue more precisely.</span></span>  
  
 <span data-ttu-id="f7c85-137">A configuração de severidade de log especificada no nível de atividade determina a configuração de severidade de log de todos os módulos que constituem a atividade.</span><span class="sxs-lookup"><span data-stu-id="f7c85-137">The log severity setting specified at the activity level determines the log severity setting of all the modules that constitute the activity.</span></span> <span data-ttu-id="f7c85-138">Entretanto, se houver qualquer conflito entre as configurações de severidade de log nos níveis de atividade e de módulo, as configurações de severidade no nível de módulo serão consideradas.</span><span class="sxs-lookup"><span data-stu-id="f7c85-138">However, if there is any conflict between the log severity settings at the activity and module levels, the severity settings at the module level are considered.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="f7c85-139">Por padrão, o módulo **Microsoft.Ssdqs.Core.Startup** está pré-configurado na seção **Avançado** com o nível de severidade definido como **Informações**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-139">By default, the **Microsoft.Ssdqs.Core.Startup** module is preconfigured in the **Advanced** section with the severity level set as **Info**.</span></span> <span data-ttu-id="f7c85-140">Isso ocorre para habilitar o log de eventos de severidade Informações e mais alta (Aviso, Erro e Fatal) que estão relacionados ao início e à interrupção de serviços do DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c85-140">This is done to enable logging of events of severity Info and higher (Warn, Error, and Fatal) that are related to starting and stopping of DQS services.</span></span>  
> -   <span data-ttu-id="f7c85-141">Você deverá configurar níveis de severidade de log apenas no nível de módulo se for um usuário do DQS avançado que esteja familiarizado com os assemblies do sistema DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c85-141">You should configure log severity levels at the module level only if you are an advanced DQS user who is familiar with the DQS system assemblies.</span></span>  
  
 <span data-ttu-id="f7c85-142">Para configurar níveis de severidade de log no nível de módulo:</span><span class="sxs-lookup"><span data-stu-id="f7c85-142">To configure log severity levels at the module level:</span></span>  
  
1.  <span data-ttu-id="f7c85-143">Na guia **Configurações de Log** , clique na seta para baixo em **Avançado** para exibir a área.</span><span class="sxs-lookup"><span data-stu-id="f7c85-143">In the **Log Settings** tab, click the down arrow against **Advanced** to display the area.</span></span>  
  
2.  <span data-ttu-id="f7c85-144">Na grade que aparece, selecione um nome do módulo da lista suspensa na coluna **Módulo** .</span><span class="sxs-lookup"><span data-stu-id="f7c85-144">In the grid that appears, select a module name from the drop-down list in the **Module** column.</span></span>  
  
3.  <span data-ttu-id="f7c85-145">Depois, selecione um nível de severidade para o módulo da lista suspensa na coluna **Severidade** .</span><span class="sxs-lookup"><span data-stu-id="f7c85-145">Next, select a severity level for the module from the drop-down list in the **Severity** column.</span></span> <span data-ttu-id="f7c85-146">Você pode selecionar uma destas opções: **Fatal**, **Erro**, **Aviso**, **Informações**e **Depuração**.</span><span class="sxs-lookup"><span data-stu-id="f7c85-146">You can select one among the following: **Fatal**, **Error**, **Warn**, **Info**, and **Debug**.</span></span>  
  
     <span data-ttu-id="f7c85-147">Por exemplo, na atividade de gerenciamento de domínio, você pode definir um nível de granularidade para a funcionalidade de definição de regra de domínio diferente da atividade de gerenciamento de domínio, selecionando o módulo **Microsoft.Ssdqs.DomainRules.Define** e um nível de severidade de log diferente.</span><span class="sxs-lookup"><span data-stu-id="f7c85-147">For example, within the domain management activity, you can set a different granularity level for the domain rule definition functionality than the domain management activity by selecting the **Microsoft.Ssdqs.DomainRules.Define** module, and selecting a different log severity level.</span></span> <span data-ttu-id="f7c85-148">Da mesma forma, você pode definir um outro nível de granularidade para a funcionalidade de regra de domínio cruzado, selecionando o módulo **Microsoft.Ssdqs.DomainRules.Condition.CrossDomain** e um nível de severidade de log diferente.</span><span class="sxs-lookup"><span data-stu-id="f7c85-148">Similarly, you can set a different granularity level for the cross-domain rule functionality by selecting the **Microsoft.Ssdqs.DomainRules.Condition.CrossDomain** module, and selecting a different log severity level.</span></span>  
  
4.  <span data-ttu-id="f7c85-149">Repita as etapas 2 e 3 para outros módulos, caso necessário.</span><span class="sxs-lookup"><span data-stu-id="f7c85-149">Repeat steps 2 and 3 for other modules, if required.</span></span> <span data-ttu-id="f7c85-150">Você também pode adicionar ou excluir linhas à grade clicando nos ícones **Adicionar Módulo** e **Remover Módulo** .</span><span class="sxs-lookup"><span data-stu-id="f7c85-150">You can also add or delete rows to the grid by clicking the **Add Module** and **Remove Module** icons.</span></span>  
  
5.  <span data-ttu-id="f7c85-151">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="f7c85-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c85-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7c85-152">See Also</span></span>  
 [<span data-ttu-id="f7c85-153">Definir configurações avançadas para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="f7c85-153">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)  
  
  
