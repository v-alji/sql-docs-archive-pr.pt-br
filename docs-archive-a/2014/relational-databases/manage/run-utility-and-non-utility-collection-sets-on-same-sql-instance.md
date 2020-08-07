---
title: Considerações sobre a execução de conjuntos de coleta do utilitário e não utilitários na mesma instância do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575115"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="b7b46-102">Considerações sobre a execução de Conjuntos de Coleta do Utilitário e não Utilitário na mesma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7b46-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="b7b46-103">O conjunto de coleta do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility tem suporte lado a lado com conjuntos de coleta não Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7b46-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="b7b46-104">Ou seja, uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ser monitorada por outros conjuntos de coleta enquanto ainda é membro de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="b7b46-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b7b46-105">No entanto, você deve desabilitar a funcionalidade de coleta de dados não [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility enquanto a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo inscrita no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="b7b46-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="b7b46-106">Depois que a instância for inscrita no UCP, você poderá reiniciar conjuntos de coleta não - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="b7b46-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="b7b46-107">Observe, no entanto, que todos os conjuntos de coleta na instância gerenciada carregarão seus dados no UMDW (data warehouse de gerenciamento do utilitário); o nome de arquivo UMDW é sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="b7b46-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="b7b46-108">Para executar conjuntos de coleta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility lado a lado com conjuntos de coleta não [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, leve em consideração os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="b7b46-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="b7b46-109">Há suporte para conjuntos de coleta lado a lado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="b7b46-110">Você deve desabilitar os coletores de dados existentes ao inscrever instâncias no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="b7b46-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="b7b46-111">Para cumprir os requisitos de validação, você deve executar os seguintes procedimentos armazenados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , antes de criar um UCP, e na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , antes de inscrevê-lo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span><span class="sxs-lookup"><span data-stu-id="b7b46-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="b7b46-112">Se você não executar esses procedimentos armazenados antes de iniciar o Assistente para Criar UCP ou o Assistente para Adicionar Instância Gerenciada, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="b7b46-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="b7b46-113">Você deve usar o UMDW (sysutility_mdw) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility para todos os conjuntos de coleta em uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7b46-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b46-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7b46-114">See Also</span></span>  
 <span data-ttu-id="b7b46-115">[Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b7b46-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="b7b46-116">Configurar o data warehouse do ponto de controle do utilitário &#40;Utilitário do SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b7b46-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
