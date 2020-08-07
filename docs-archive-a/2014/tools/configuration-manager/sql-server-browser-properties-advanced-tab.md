---
title: Propriedades do SQL Server Browser (guia Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582236"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="35a2b-102">Propriedades do Navegador do SQL Server (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="35a2b-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="35a2b-103">O programa Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado como um serviço no servidor.</span><span class="sxs-lookup"><span data-stu-id="35a2b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="35a2b-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser escuta as solicitações de entrada de recursos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações sobre as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="35a2b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="35a2b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="35a2b-105">Options</span></span>  
 <span data-ttu-id="35a2b-106">**Clusterizado**</span><span class="sxs-lookup"><span data-stu-id="35a2b-106">**Clustered**</span></span>  
 <span data-ttu-id="35a2b-107">Indica se este serviço for instalado como um recurso de um servidor clusterizado.</span><span class="sxs-lookup"><span data-stu-id="35a2b-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="35a2b-108">**Relatório de Comentários do Cliente**</span><span class="sxs-lookup"><span data-stu-id="35a2b-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="35a2b-109">Indica se o Monitoramento da Qualidade do Serviço foi habilitado neste serviço.</span><span class="sxs-lookup"><span data-stu-id="35a2b-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="35a2b-110">Para obter mais informações sobre o Relatório de Comentários do Cliente, pesquise "Configurações de relatório de erro e uso" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="35a2b-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="35a2b-111">**Diretório de Despejo**</span><span class="sxs-lookup"><span data-stu-id="35a2b-111">**Dump Directory**</span></span>  
 <span data-ttu-id="35a2b-112">O local em que os despejos de memória são colocadas no caso de um erro.</span><span class="sxs-lookup"><span data-stu-id="35a2b-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="35a2b-113">**Relatório de Erros**</span><span class="sxs-lookup"><span data-stu-id="35a2b-113">**Error Reporting**</span></span>  
 <span data-ttu-id="35a2b-114">Quando definido como **Sim**, o programa Dr. Watson encaminhará informações para a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou para o servidor de erro, se ocorrer uma falha grave.</span><span class="sxs-lookup"><span data-stu-id="35a2b-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="35a2b-115">Para obter mais informações sobre o Relatório de Erros, pesquise "Configurações de relatório de erro e uso" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="35a2b-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="35a2b-116">**ID da Instância**</span><span class="sxs-lookup"><span data-stu-id="35a2b-116">**Instance ID**</span></span>  
 <span data-ttu-id="35a2b-117">Indica a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usou essa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="35a2b-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="35a2b-118">A instância padrão é **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="35a2b-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a2b-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35a2b-119">See Also</span></span>  
 [<span data-ttu-id="35a2b-120">Serviço Navegador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="35a2b-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
