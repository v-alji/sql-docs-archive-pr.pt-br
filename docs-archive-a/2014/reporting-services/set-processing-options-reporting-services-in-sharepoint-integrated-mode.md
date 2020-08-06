---
title: Definir opções de processamento (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680809"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="9b39a-102">Definir opções de processamento (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="9b39a-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="9b39a-103">Você pode definir opções de processamento em um relatório [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para determinar quando ocorre o processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="9b39a-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="9b39a-104">Pode também definir um valor de tempo limite para o processamento de relatórios, além de opções que determinam se o histórico de relatórios está habilitado para o relatório atual.</span><span class="sxs-lookup"><span data-stu-id="9b39a-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="9b39a-105">Você pode executar um relatório como instantâneo de relatório para evitar que o relatório seja executado em momentos arbitrários (durante um backup agendado, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="9b39a-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="9b39a-106">Um instantâneo de relatório normalmente é criado e, em seguida, atualizado de acordo com um agendamento, permitindo marcar o horário exato em que ocorrerá o processamento de dados e do relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="9b39a-107">Se um relatório basear-se em consultas cujo processamento seja demorado ou que utilizem dados de uma fonte de dados que prefira que não seja acessada durante determinadas horas, você deverá executar o relatório como instantâneo.</span><span class="sxs-lookup"><span data-stu-id="9b39a-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="9b39a-108">Um servidor de relatório pode armazenar em cache uma cópia de um relatório processado e devolvê-la quando um usuário abrir o relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="9b39a-109">O armazenamento em cache é uma técnica de aprimoramento de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9b39a-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="9b39a-110">O armazenamento em cache pode diminuir o tempo necessário para recuperar um relatório, caso ele seja grande ou acessado frequentemente.</span><span class="sxs-lookup"><span data-stu-id="9b39a-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="9b39a-111">Um histórico de relatórios é uma coleção de cópias de um relatório executadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9b39a-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="9b39a-112">É possível usar o histórico de relatórios para manter ao longo do tempo um registro de um relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="9b39a-113">Um histórico de relatórios não se destina a relatórios que contenham dados confidenciais ou pessoais.</span><span class="sxs-lookup"><span data-stu-id="9b39a-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="9b39a-114">Por este motivo, um histórico de relatórios pode incluir somente os relatórios que consultem uma fonte de dados utilizando um conjunto único de credenciais (armazenadas ou usadas para a execução de um relatório de forma autônoma) disponível para todos os usuários que executem um relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="9b39a-115">com o SharePoint utiliza recursos de gerenciamento de inserção e extração de conteúdo do SharePoint para salvar atualizações em tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b39a-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="9b39a-116">isso inclui a criação de instantâneos de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9b39a-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="9b39a-117">Portanto, se você ativou o controle de versões em uma biblioteca de documentos, verá a versão de relatório atualizada quando um novo instantâneo de histórico de relatórios for criado.</span><span class="sxs-lookup"><span data-stu-id="9b39a-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="9b39a-118">Esse é um efeito colateral de atualizar instantâneos.</span><span class="sxs-lookup"><span data-stu-id="9b39a-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="9b39a-119">Quando um instantâneo é atualizado, ele faz com que a propriedade LastExecution do relatório se altere, e isso causa uma alteração na versão do relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="9b39a-120">Você pode especificar valores de tempo limite para definir limites para o uso dos recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="9b39a-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="9b39a-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="9b39a-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="9b39a-122">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="9b39a-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="9b39a-123">Para definir opções de atualização de dados</span><span class="sxs-lookup"><span data-stu-id="9b39a-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="9b39a-124">Para definir opções de cache de relatório</span><span class="sxs-lookup"><span data-stu-id="9b39a-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="9b39a-125">Para definir valores de tempo limite de processamento</span><span class="sxs-lookup"><span data-stu-id="9b39a-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="9b39a-126">Para definir opções e limites de histórico de relatórios</span><span class="sxs-lookup"><span data-stu-id="9b39a-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="9b39a-127">Definir tempo limite de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9b39a-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="9b39a-128">Para definir opções de atualização de dados</span><span class="sxs-lookup"><span data-stu-id="9b39a-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="9b39a-129">Aponte para um relatório na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9b39a-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="9b39a-130">Clique na seta para baixo e selecione **Gerenciar opções de processamento**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="9b39a-131">Em **Opções de Atualização de Dados**, clique em **Usar dados de instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="9b39a-132">Se você vir a mensagem " Este relatório não pode ser executado a partir de um instantâneo porque uma ou mais das credenciais de fontes de dados não estão armazenadas", isto significa que o relatório não está configurado para ser executado de forma autônoma e que você deve modificar as fontes de dados para usar credenciais armazenadas antes de definir esta opção.</span><span class="sxs-lookup"><span data-stu-id="9b39a-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="9b39a-133">Em **Opções de Instantâneo de Dados**, selecione **Agendar processamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="9b39a-134">Selecione **Em uma agenda compartilhada** se você tiver uma agenda compartilhada que deseje usar; caso contrário, clique em **Em uma agenda personalizada**e em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="9b39a-135">Selecione a frequência, o agendamento, as datas de início e término e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9b39a-136">Em **Opções de Instantâneo de Dados**, selecione **Criar ou atualizar o instantâneo quando esta página for salva** se você quiser criar imediatamente dados de instantâneo para serem usados com o relatório, sem aguardar o processamento de dados agendado.</span><span class="sxs-lookup"><span data-stu-id="9b39a-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="9b39a-137">Para definir opções de cache de relatório</span><span class="sxs-lookup"><span data-stu-id="9b39a-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="9b39a-138">Aponte para um relatório na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9b39a-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="9b39a-139">Clique na seta para baixo e selecione **Gerenciar opções de processamento**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="9b39a-140">Em **Opções de Atualização de Dados**, clique em **Usar dados armazenados em cache**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="9b39a-141">Se você vir a mensagem "Não é possível armazenar este relatório em cache porque uma ou mais das credenciais de fonte de dados não estão armazenadas", isto significa que o relatório não está configurado para ser executado de forma autônoma e que você deve modificar as fontes de dados para usar credenciais armazenadas antes de definir esta opção.</span><span class="sxs-lookup"><span data-stu-id="9b39a-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="9b39a-142">Em **Opções de Cache**, especifique como o cache expirará:</span><span class="sxs-lookup"><span data-stu-id="9b39a-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="9b39a-143">Insira um número de minutos após o qual o cache expirará.</span><span class="sxs-lookup"><span data-stu-id="9b39a-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="9b39a-144">Use uma agenda compartilhada para limpar o cache nos horários especificados na agenda.</span><span class="sxs-lookup"><span data-stu-id="9b39a-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="9b39a-145">Crie uma agenda compartilhada para limpar o cache em um horário especificado por você.</span><span class="sxs-lookup"><span data-stu-id="9b39a-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="9b39a-146">Para definir valores de tempo limite de processamento</span><span class="sxs-lookup"><span data-stu-id="9b39a-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="9b39a-147">Aponte para um relatório na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9b39a-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="9b39a-148">Clique na seta para baixo e selecione **Gerenciar opções de processamento**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="9b39a-149">Em **Tempo Limite de Processamento**, selecione **Usar a configuração padrão do site** se você quiser usar o valor especificado no nível do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="9b39a-150">Caso contrário, selecione **Não especificar tempo limite para processamento de relatório** ou **Limitar o processamento de relatórios em segundos** se quiser substituir esse valor para que não haja tempo limite ou para que haja outros valores de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9b39a-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="9b39a-151">Para definir as opções e os limites do histórico de relatórios</span><span class="sxs-lookup"><span data-stu-id="9b39a-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="9b39a-152">Aponte para um relatório na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9b39a-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="9b39a-153">Clique na seta para baixo e selecione **Gerenciar opções de processamento**.</span><span class="sxs-lookup"><span data-stu-id="9b39a-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="9b39a-154">Em **Opções de Instantâneo de Histórico**, especifique como e quando o processamento de dados ocorre e é salvo.</span><span class="sxs-lookup"><span data-stu-id="9b39a-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="9b39a-155">Em **Limites de Instantâneo de Histórico**, selecione **Usar a configuração padrão do site** se desejar usar o valor especificado no nível do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9b39a-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="9b39a-156">Caso contrário, selecione **Não limitar o número de instantâneos** ou **Limitar o número de instantâneos** para especificar um valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b39a-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="9b39a-157">Definir tempo limite do banco de dados</span><span class="sxs-lookup"><span data-stu-id="9b39a-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="9b39a-158">Use o Windows PowerShell para definir o tempo limite de banco de dados de um servidor de relatório do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9b39a-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="9b39a-159">Para obter mais informações, confira a seção "Obter e definir Propriedades do banco de dados do aplicativo de serviço de relatório" de [Cmdlets do PowerShell para o modo do SharePoint do Reporting Services](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9b39a-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b39a-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b39a-160">See Also</span></span>  
 <span data-ttu-id="9b39a-161">[Definir propriedades de processamento de relatório](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9b39a-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="9b39a-162">[Armazenando relatórios em cache &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b39a-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="9b39a-163">Definindo valores de tempo limite para processamento de relatórios e conjuntos de dados compartilhados &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b39a-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
