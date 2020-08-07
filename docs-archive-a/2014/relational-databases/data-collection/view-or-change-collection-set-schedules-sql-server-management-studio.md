---
title: Exibir ou alterar agendas de conjuntos de coleta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581956"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="49eb2-102">Exibir ou alterar agendas de conjuntos de coleta (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="49eb2-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="49eb2-103">É possível exibir ou alterar agendas de conjuntos de coleta usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49eb2-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="49eb2-104">O modo de coleta, armazenado em cache ou não, determina como você pode fazer alterações em uma agenda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="49eb2-105">O modo cache usa agendas separadas para coleção e carregamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="49eb2-106">O modo não cache usa a mesma agenda para coleta e carregamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="49eb2-107">O tipo de modo de coleta de cada um dos conjuntos de coleta de Dados do Sistema é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="49eb2-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="49eb2-108">**Uso do Disco** usa o modo de coleta não cache.</span><span class="sxs-lookup"><span data-stu-id="49eb2-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="49eb2-109">**Estatísticas de Consulta** usa o modo cache de coleção.</span><span class="sxs-lookup"><span data-stu-id="49eb2-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="49eb2-110">**Atividade do Servidor** usa o modo cache de coleção.</span><span class="sxs-lookup"><span data-stu-id="49eb2-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="49eb2-111">Para exibir agendas de conjuntos de coleta</span><span class="sxs-lookup"><span data-stu-id="49eb2-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="49eb2-112">No Pesquisador de Objetos, expanda o nó **Gerenciamento** , expanda **Coleta de Dados**e, em seguida, **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="49eb2-113">Clique com o botão direito do mouse no nome do conjunto de coleta e clique em **Propriedades** para abrir a caixa de diálogo [Propriedades do Conjunto de Coleta de Dados](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="49eb2-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="49eb2-114">Para alterar as agendas para um conjunto de coleta no modo cache</span><span class="sxs-lookup"><span data-stu-id="49eb2-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="49eb2-115">No Pesquisador de Objetos, expanda o nó **Gerenciamento** , expanda **Coleta de Dados**e, em seguida, **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="49eb2-116">Clique com o botão direito do mouse em um conjunto de coleta que usa o modo cache, como **Estatísticas de Consulta**, e clique em **Propriedades** para abrir a caixa de diálogo [Propriedades do Conjunto de Coleta de Dados](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="49eb2-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="49eb2-117">Você pode alterar a frequência da coleta na página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="49eb2-118">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="49eb2-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="49eb2-119">No painel de detalhes, clique duas vezes no número exibido para a coluna **Frequência de Coleta (s)** na tabela **Itens da coleta** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="49eb2-120">Para aumentar ou reduzir a frequência da coleta, digite um número inferior ou superior e pressione ENTER para armazenar o novo valor.</span><span class="sxs-lookup"><span data-stu-id="49eb2-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="49eb2-121">Para alterar a agenda de carregamento existente para o conjunto de coleta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="49eb2-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="49eb2-122">Clique na página **Carregamentos** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="49eb2-123">No painel de detalhes, clique em **Escolher**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="49eb2-124">A caixa de diálogo **Escolher Agenda para o Trabalho** é aberta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="49eb2-125">As agendas disponíveis aparecem como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="49eb2-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="49eb2-126">Clique na linha que contém a agenda desejada.</span><span class="sxs-lookup"><span data-stu-id="49eb2-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="49eb2-127">Por exemplo, para alterar o agendamento a cada 5 minutos, clique na linha em que o nome de agendamento é **CollectorSchedule_Every_5min.**</span><span class="sxs-lookup"><span data-stu-id="49eb2-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="49eb2-128">É possível exibir e editar as propriedades da agenda selecionada clicando em **Propriedades** para abrir a caixa de diálogo **Propriedades da Agenda de Trabalho** da agenda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="49eb2-129">Você pode usar essa caixa de diálogo para alterar as informações da agenda, como a frequência.</span><span class="sxs-lookup"><span data-stu-id="49eb2-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="49eb2-130">Como alternativa à modificação de uma agenda existente, você pode criar uma nova agenda de carregamento clicando em **Nova** na página **Carregamentos** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="49eb2-131">Essa ação abre a caixa de diálogo **Nova Agenda de Trabalho** que pode ser usada para criar uma agenda personalizada.</span><span class="sxs-lookup"><span data-stu-id="49eb2-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="49eb2-132">Ao concluir a configuração da agenda, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="49eb2-133">As alteração feitas aparecem na página **Carregamentos** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="49eb2-134">Clique em **OK** para salvar as alterações na frequência da coleta e na agenda de carregamento e para fechar a caixa de diálogo **Propriedades do Conjunto de Coleta de Dados** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="49eb2-135">Para alterar a agenda de um conjunto de coleta no modo não cache</span><span class="sxs-lookup"><span data-stu-id="49eb2-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="49eb2-136">No Pesquisador de Objetos, expanda o nó **Gerenciamento** , expanda **Coleta de Dados**e, em seguida, **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="49eb2-137">Clique com o botão direito do mouse em um conjunto de coleta que usa o modo não cache, como **Uso do Disco**, e clique em **Propriedades** para abrir a caixa de diálogo [Propriedades do Conjunto de Coleta de Dados](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="49eb2-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="49eb2-138">A caixa de diálogo **Propriedades do Conjunto de Coleta de Dados** exibe uma exibição paginada das propriedades do conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="49eb2-139">Para alterar a agenda para o conjunto de coleta, clique em **Escolher**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="49eb2-140">A caixa de diálogo **Escolher Agenda para o Trabalho** é aberta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="49eb2-141">As agendas disponíveis são exibidas como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="49eb2-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="49eb2-142">Clique na linha que contém a agenda desejada.</span><span class="sxs-lookup"><span data-stu-id="49eb2-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="49eb2-143">Por exemplo, para alterar o agendamento a cada 5 minutos, clique na linha em que o nome de agendamento é **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49eb2-144">É possível exibir e editar as propriedades da agenda selecionada clicando em **Propriedades** para abrir a caixa de diálogo **Propriedades da Agenda de Trabalho** da agenda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="49eb2-145">Você pode usar essa caixa de diálogo para alterar as informações da agenda, como a frequência.</span><span class="sxs-lookup"><span data-stu-id="49eb2-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="49eb2-146">Como alternativa à modificação de uma agenda existente, você pode criar uma nova agenda de carregamento e de coleta clicando em **Nova** na página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="49eb2-147">Essa ação abre a caixa de diálogo **Nova Agenda de Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="49eb2-148">Ao concluir a configuração da agenda, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="49eb2-149">Clique em **OK** para salvar as alterações e fechar a caixa de diálogo **Propriedades do Conjunto de Coleta de Dados** .</span><span class="sxs-lookup"><span data-stu-id="49eb2-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="49eb2-150">Caixa de diálogo Propriedades de Conjunto de Coleta de Dados</span><span class="sxs-lookup"><span data-stu-id="49eb2-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="49eb2-151">**Página Geral**</span><span class="sxs-lookup"><span data-stu-id="49eb2-151">**General Page**</span></span>  
  
 <span data-ttu-id="49eb2-152">Use esta página para configurar o modo como os dados devem ser coletados e carregados, para configurar cronogramas e configurar períodos de retenção de dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="49eb2-153">Esta página fornece também informações sobre conjuntos de coleta, como tipos de coletor e frequências de coleta, além de parâmetros de entrada usados em um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="49eb2-154">**Nome**</span><span class="sxs-lookup"><span data-stu-id="49eb2-154">**Name**</span></span>  
 <span data-ttu-id="49eb2-155">Exibe o nome do conjunto de coleta ao qual a página se refere.</span><span class="sxs-lookup"><span data-stu-id="49eb2-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="49eb2-156">**Coleta e carregamento de dados**</span><span class="sxs-lookup"><span data-stu-id="49eb2-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="49eb2-157">Especifica de que modo os dados são coletados e carregados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="49eb2-158">Clique em uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="49eb2-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49eb2-159">**Sem-cache. Coleta e upload de dados na mesma agenda.**</span><span class="sxs-lookup"><span data-stu-id="49eb2-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="49eb2-160">Quando selecionada, especifique uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="49eb2-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="49eb2-161">**Sob demanda**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-161">**On-demand**.</span></span> <span data-ttu-id="49eb2-162">Os dados são coletados e carregados sob demanda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="49eb2-163">**Agenda**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-163">**Schedule**.</span></span> <span data-ttu-id="49eb2-164">Os dados são coletados e carregados de acordo com a agenda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="49eb2-165">Clique em **Escolher** para selecionar em uma lista predefinida de agendas ou clique em **Novo** para criar uma nova agenda.</span><span class="sxs-lookup"><span data-stu-id="49eb2-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="49eb2-166">**Em cache. Coletar e armazenar os dados em cache em um conjunto de frequências de coleta. Carregar os dados armazenados em cache em uma agenda separada.**</span><span class="sxs-lookup"><span data-stu-id="49eb2-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="49eb2-167">Colete e armazene os dados em cache para uma frequência de coleta especificada.</span><span class="sxs-lookup"><span data-stu-id="49eb2-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="49eb2-168">Carregue os dados coletados em uma agenda separada.</span><span class="sxs-lookup"><span data-stu-id="49eb2-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="49eb2-169">**Itens da coleta**</span><span class="sxs-lookup"><span data-stu-id="49eb2-169">**Collection items**</span></span>  
 <span data-ttu-id="49eb2-170">Exibe os itens de coleção no conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="49eb2-171">São fornecidas as informações a seguir para cada item de coleta:</span><span class="sxs-lookup"><span data-stu-id="49eb2-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="49eb2-172">**Nome**</span><span class="sxs-lookup"><span data-stu-id="49eb2-172">**Name**</span></span>  
  
-   <span data-ttu-id="49eb2-173">**Tipo de Coletor**</span><span class="sxs-lookup"><span data-stu-id="49eb2-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="49eb2-174">**Frequência de Coleta** (segundos).</span><span class="sxs-lookup"><span data-stu-id="49eb2-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="49eb2-175">Este campo pode ser editado se **Coleta e carregamento de dados** for configurado como em cache.</span><span class="sxs-lookup"><span data-stu-id="49eb2-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="49eb2-176">Clique duas vezes nesta célula para definir a frequência de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="49eb2-177">**Parâmetros de entrada**</span><span class="sxs-lookup"><span data-stu-id="49eb2-177">**Input parameters**</span></span>  
 <span data-ttu-id="49eb2-178">Exibe os parâmetros de entrada usados no conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="49eb2-179">**Executar como**</span><span class="sxs-lookup"><span data-stu-id="49eb2-179">**Run as**</span></span>  
 <span data-ttu-id="49eb2-180">Especifica a conta usada para executar o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="49eb2-181">Por padrão, essa é a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Conta de Serviço do Agent.</span><span class="sxs-lookup"><span data-stu-id="49eb2-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="49eb2-182">Se contas proxy estiverem definidas, a lista incluirá os nomes das contas proxy disponíveis.</span><span class="sxs-lookup"><span data-stu-id="49eb2-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="49eb2-183">**Definir por quanto tempo serão retidos dados coletados no data warehouse de gerenciamento.**</span><span class="sxs-lookup"><span data-stu-id="49eb2-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="49eb2-184">Especifica por quanto tempo os dados coletados serão retidos.</span><span class="sxs-lookup"><span data-stu-id="49eb2-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="49eb2-185">Clique em uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="49eb2-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49eb2-186">**Reter dados para**</span><span class="sxs-lookup"><span data-stu-id="49eb2-186">**Retain data for**</span></span>|<span data-ttu-id="49eb2-187">Esta opção fica selecionada por padrão e o período de retenção padrão é de 14 dias.</span><span class="sxs-lookup"><span data-stu-id="49eb2-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="49eb2-188">**Reter dados indefinidamente**</span><span class="sxs-lookup"><span data-stu-id="49eb2-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="49eb2-189">Não há nenhum limite no período de tempo em que os dados são retidos.</span><span class="sxs-lookup"><span data-stu-id="49eb2-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="49eb2-190">**Página Carregamentos**</span><span class="sxs-lookup"><span data-stu-id="49eb2-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="49eb2-191">Use esta página para configurar a agenda de carregamento de dados coletados por esse conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49eb2-192">Esta guia só estará habilitada se a opção **Em cache** for configurada para **Coleta e carregamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="49eb2-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="49eb2-193">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="49eb2-193">**Server**</span></span>  
 <span data-ttu-id="49eb2-194">Exibe o nome do servidor que hospeda o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="49eb2-195">Para obter mais informações, veja [Configurar o data warehouse de gerenciamento &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="49eb2-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="49eb2-196">**Data warehouse de gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="49eb2-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="49eb2-197">Exibe o nome do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49eb2-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="49eb2-198">Para obter mais informações, veja [Configurar o data warehouse de gerenciamento &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="49eb2-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="49eb2-199">**Último carregamento**</span><span class="sxs-lookup"><span data-stu-id="49eb2-199">**Last upload**</span></span>  
 <span data-ttu-id="49eb2-200">Exibe informações de data e hora do último carregamento feito para o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="49eb2-201">**Agenda de carregamento**</span><span class="sxs-lookup"><span data-stu-id="49eb2-201">**Upload schedule**</span></span>  
 <span data-ttu-id="49eb2-202">Especifica a agenda de carregamento do conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="49eb2-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="49eb2-203">E estiver habilitada, clique em **Escolher** para selecionar em uma lista predefinida de agendas ou clique em **Novo** para criar uma agenda nova.</span><span class="sxs-lookup"><span data-stu-id="49eb2-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="49eb2-204">**Página Descrição**</span><span class="sxs-lookup"><span data-stu-id="49eb2-204">**Description Page**</span></span>  
  
 <span data-ttu-id="49eb2-205">Use esta página para exibir uma descrição do conjunto de coleta ao qual essa página de propriedades se refere.</span><span class="sxs-lookup"><span data-stu-id="49eb2-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49eb2-206">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="49eb2-206">See Also</span></span>  
 <span data-ttu-id="49eb2-207">[Gerenciar coleta de dados](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="49eb2-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="49eb2-208">Coleta de Dados</span><span class="sxs-lookup"><span data-stu-id="49eb2-208">Data Collection</span></span>](data-collection.md)  
  
  
