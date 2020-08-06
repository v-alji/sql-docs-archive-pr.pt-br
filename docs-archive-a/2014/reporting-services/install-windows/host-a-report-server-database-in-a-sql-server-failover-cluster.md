---
title: Hospedar um banco de dados do servidor de relatório em um cluster de failover do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 921ce03fd08e7820266b828d5848f64db1e257ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680833"
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a><span data-ttu-id="16e6c-102">Hospedar um banco de dados do servidor de relatório em um cluster de failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="16e6c-102">Host a Report Server Database in a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="16e6c-103">oferece suporte de clustering de failover, permitindo o uso de vários discos para uma ou mais instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16e6c-103">provides failover clustering support so that you can use multiple disks for one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances.</span></span> <span data-ttu-id="16e6c-104">O clustering de failover tem suporte somente para o banco de dados do servidor de relatório; não é possível executar o serviço Servidor de Relatório como parte de um cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="16e6c-104">Failover clustering is supported only for the report server database; you cannot run the Report Server service as part of a failover cluster.</span></span>  
  
 <span data-ttu-id="16e6c-105">Para hospedar um banco de dados do servidor de relatório em um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o cluster já deve estar instalado e configurado.</span><span class="sxs-lookup"><span data-stu-id="16e6c-105">To host a report server database on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the cluster must already be installed and configured.</span></span> <span data-ttu-id="16e6c-106">Você pode selecionar o cluster de failover como o nome do servidor ao criar o banco de dados do servidor de relatório na página Configuração do Banco de Dados da ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16e6c-106">You can then select the failover cluster as the server name when you create the report server database in the Database Setup page of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="16e6c-107">Embora o serviço Servidor de Relatório não possa participar de um cluster de failover, é possível instalar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um computador que tenha um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="16e6c-107">Although the Report Server service cannot participate in a failover cluster, you can install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a computer that has a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster installed.</span></span> <span data-ttu-id="16e6c-108">O servidor de relatório é executado de maneira independente do cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="16e6c-108">The report server runs independently of the failover cluster.</span></span> <span data-ttu-id="16e6c-109">Se você instalar um servidor de relatório em um computador que tenha uma instância de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não será preciso usar o cluster de failover para o banco de dados do servidor de relatório; você poderá usar outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para hospedar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="16e6c-109">If you install a report server on a computer that is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover instance, you are not required to use the failover cluster for the report server database; you can use a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e6c-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16e6c-110">See Also</span></span>  
 <span data-ttu-id="16e6c-111">[Banco de dados do servidor de relatório &#40;modo nativo do SSRS&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="16e6c-111">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="16e6c-112">Criar um banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="16e6c-112">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
  
  
