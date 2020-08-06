---
title: Propriedades de banco de dados (página Envio de Logs de Transações) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685759"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="7dd50-102">Propriedades de banco de dados (página Envio do Logs de Transações)</span><span class="sxs-lookup"><span data-stu-id="7dd50-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="7dd50-103">Use essa página para configurar e modificar as propriedades de envio de logs para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7dd50-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="7dd50-104">Para obter uma explicação dos conceitos de envio de log, veja [Sobre o envio de logs &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7dd50-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7dd50-105">Opções</span><span class="sxs-lookup"><span data-stu-id="7dd50-105">Options</span></span>  
 <span data-ttu-id="7dd50-106">**Habilitar como banco de dados primário em uma configuração de envio de logs**</span><span class="sxs-lookup"><span data-stu-id="7dd50-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="7dd50-107">Habilita esse banco de dados como banco de dados primário para envio de logs.</span><span class="sxs-lookup"><span data-stu-id="7dd50-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="7dd50-108">Selecione-o e, em seguida, configure as opções restantes na página.</span><span class="sxs-lookup"><span data-stu-id="7dd50-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="7dd50-109">Se você desmarcar essa caixa de seleção, a configuração de envio de logs será descartada para esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7dd50-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="7dd50-110">**Configurações de Backup**</span><span class="sxs-lookup"><span data-stu-id="7dd50-110">**Backup Settings**</span></span>  
 <span data-ttu-id="7dd50-111">Clique em **Configurações de Backup** para configurar o agendamento de backup, local, alerta e parâmetros de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7dd50-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="7dd50-112">**Agenda do Backup**</span><span class="sxs-lookup"><span data-stu-id="7dd50-112">**Backup schedule**</span></span>  
 <span data-ttu-id="7dd50-113">Mostra a agenda de backup selecionada presentemente para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7dd50-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="7dd50-114">Clique em **Configurações de Backup** para modificar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="7dd50-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="7dd50-115">**Último Backup Criado**</span><span class="sxs-lookup"><span data-stu-id="7dd50-115">**Last backup created**</span></span>  
 <span data-ttu-id="7dd50-116">Indica hora e data do último backup de log da transação do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7dd50-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="7dd50-117">**Instâncias e bancos de dados do servidor secundário**</span><span class="sxs-lookup"><span data-stu-id="7dd50-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="7dd50-118">Lista os servidores secundários presentemente configurados e os bancos de dados desse banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7dd50-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="7dd50-119">Destaque um banco de dados e depois clique em **...** para modificar os parâmetros associados àquele banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="7dd50-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="7dd50-120">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="7dd50-120">**Add**</span></span>  
 <span data-ttu-id="7dd50-121">Clique em **Adicionar** para adicionar um banco de dados secundário à configuração de envio de logs para esse banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7dd50-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="7dd50-122">**Remover**</span><span class="sxs-lookup"><span data-stu-id="7dd50-122">**Remove**</span></span>  
 <span data-ttu-id="7dd50-123">Remove um banco de dados selecionado dessa configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="7dd50-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="7dd50-124">Selecione primeiramente o banco de dados, depois clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="7dd50-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="7dd50-125">**Use uma instância do servidor monitor**</span><span class="sxs-lookup"><span data-stu-id="7dd50-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="7dd50-126">Define uma instância de servidor monitor para essa configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="7dd50-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="7dd50-127">Marque a caixa de seleção **Usar uma Instância de Servidor Monitor** , depois clique em **Configurações** para especificar a instância de servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="7dd50-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="7dd50-128">**Instância de Servidor Monitor**</span><span class="sxs-lookup"><span data-stu-id="7dd50-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="7dd50-129">Indica a instância de servidor monitor atualmente configurada para essa configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="7dd50-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="7dd50-130">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="7dd50-130">**Settings**</span></span>  
 <span data-ttu-id="7dd50-131">Configura a instância de servidor monitor para uma configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="7dd50-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="7dd50-132">Clique em **Configurações** para configurar essa instância de servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="7dd50-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="7dd50-133">**Configuração do Script**</span><span class="sxs-lookup"><span data-stu-id="7dd50-133">**Script Configuration**</span></span>  
 <span data-ttu-id="7dd50-134">Gera um script para configuração do envio de logs com os parâmetros selecionados.</span><span class="sxs-lookup"><span data-stu-id="7dd50-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="7dd50-135">Clique em **Configuração do script**, depois selecione um destino de saída para o script.</span><span class="sxs-lookup"><span data-stu-id="7dd50-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7dd50-136">Antes de gerar scripts de configurações para um banco de dados secundário, é preciso chamar a caixa de diálogo **Configurações do Banco de Dados Secundário** .</span><span class="sxs-lookup"><span data-stu-id="7dd50-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="7dd50-137">Chamar essa caixa de diálogo conecta você ao servidor secundário e recupera as configurações atuais do banco de dados secundário que são necessárias para gerar o script.</span><span class="sxs-lookup"><span data-stu-id="7dd50-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd50-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dd50-138">See Also</span></span>  
 <span data-ttu-id="7dd50-139">[Procedimentos armazenados de envio de logs &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dd50-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="7dd50-140">Tabelas de envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7dd50-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  
