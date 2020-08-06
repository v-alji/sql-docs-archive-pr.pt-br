---
title: Configurações do Monitor de Envio de Logs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685738"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="05266-102">Configurações do monitor de envio de logs</span><span class="sxs-lookup"><span data-stu-id="05266-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="05266-103">Use essa página para configurar e modificar as propriedades do servidor monitor para envio de logs.</span><span class="sxs-lookup"><span data-stu-id="05266-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="05266-104">Para obter uma explicação dos conceitos de envio de log, veja [Sobre o envio de logs &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="05266-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="05266-105">Opções</span><span class="sxs-lookup"><span data-stu-id="05266-105">Options</span></span>  
 <span data-ttu-id="05266-106">**Instância de Servidor Monitor**</span><span class="sxs-lookup"><span data-stu-id="05266-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="05266-107">Exibe o nome da instância do servidor configurada presentemente como servidor monitor para a configuração do envio de logs.</span><span class="sxs-lookup"><span data-stu-id="05266-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="05266-108">**Connect**</span><span class="sxs-lookup"><span data-stu-id="05266-108">**Connect**</span></span>  
 <span data-ttu-id="05266-109">Escolha e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usada como servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="05266-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="05266-110">A conta usada para conexão precisa ser membro da função de servidor fixa sysadmin na instância de servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="05266-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="05266-111">**Representando a conta proxy do trabalho**</span><span class="sxs-lookup"><span data-stu-id="05266-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="05266-112">Faça com que o envio de logs represente a conta do proxy do SQL Server Agent quando conectar-se à instância do servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="05266-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="05266-113">Os processos de backup, cópia e restauração precisam estar preparados para conexão com o servidor monitor para atualizar o status das operações de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="05266-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="05266-114">**Usando o seguinte logon do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="05266-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="05266-115">Permita que o envio de logs use um logon [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] específico na conexão com a instância do servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="05266-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="05266-116">Os processos de backup, cópia e restauração precisam estar preparados para conexão com o servidor monitor para atualizar o status das operações de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="05266-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="05266-117">Selecione essa opção para que o envio de logs use um logon específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Em seguida, especifique logon e senha.</span><span class="sxs-lookup"><span data-stu-id="05266-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="05266-118">**Excluir histórico após**</span><span class="sxs-lookup"><span data-stu-id="05266-118">**Delete history after**</span></span>  
 <span data-ttu-id="05266-119">Especifique o número de horas em que as informações do histórico do log de envio no servidor monitor serão retidas antes de serem excluídas.</span><span class="sxs-lookup"><span data-stu-id="05266-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="05266-120">**Nome do trabalho**</span><span class="sxs-lookup"><span data-stu-id="05266-120">**Job name**</span></span>  
 <span data-ttu-id="05266-121">Indica o nome do trabalho de alerta do SQL Server Agent usado pelo envio de logs para gerar alertas quando os limites de backup e restauração forem excedidos.</span><span class="sxs-lookup"><span data-stu-id="05266-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="05266-122">Ao criar esse trabalho pela primeira vez, é possível alterar o nome digitando-o na caixa.</span><span class="sxs-lookup"><span data-stu-id="05266-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="05266-123">**Agenda**</span><span class="sxs-lookup"><span data-stu-id="05266-123">**Schedule**</span></span>  
 <span data-ttu-id="05266-124">Indica a agenda atual do trabalho de alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="05266-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="05266-125">**Editar**</span><span class="sxs-lookup"><span data-stu-id="05266-125">**Edit**</span></span>  
 <span data-ttu-id="05266-126">Modifique os parâmetros do trabalho de alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="05266-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="05266-127">**Desabilitar este trabalho**</span><span class="sxs-lookup"><span data-stu-id="05266-127">**Disable this job**</span></span>  
 <span data-ttu-id="05266-128">Suspender o trabalho de alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="05266-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
