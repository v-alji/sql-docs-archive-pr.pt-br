---
title: Reporting Services no SQL Server Management Studio (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683384"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="407c9-102">Reporting Services no SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="407c9-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="407c9-103">Os administradores de servidor de relatório podem usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="407c9-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="407c9-104">Habilitar recursos, definir padrões de servidor e gerenciar trabalhos em execução.</span><span class="sxs-lookup"><span data-stu-id="407c9-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="407c9-105">Exibir e criar relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="407c9-105">View and create custom reports.</span></span> <span data-ttu-id="407c9-106">No Pesquisador de Objetos, muitos nós exibem um conjunto de relatórios padrão instalados com o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="407c9-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="407c9-107">Você deve ter permissões de administrador.</span><span class="sxs-lookup"><span data-stu-id="407c9-107">You must have administrator permissions.</span></span> <span data-ttu-id="407c9-108">O esquema de um relatório personalizado deve corresponder ao esquema dos relatórios instalados.</span><span class="sxs-lookup"><span data-stu-id="407c9-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="407c9-109">Para obter mais informações, consulte [Relatórios personalizados no Management Studio](../../ssms/object/custom-reports-in-management-studio.md) e [Localizar a versão do esquema de definição de relatório &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="407c9-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="407c9-110">Os autores de relatório podem usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="407c9-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="407c9-111">Visualizar dados espaciais de um conjunto de resultados da consulta para um relatório de mapa.</span><span class="sxs-lookup"><span data-stu-id="407c9-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="407c9-112">Depois de executar a consulta, use a tabela **Resultados espaciais** no painel do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="407c9-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="407c9-113">Para obter mais informações, consulte [Como exibir dados espaciais no Pesquisador de Objetos](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="407c9-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="407c9-114">Esta seção contém instruções passo a passo para a execução de várias tarefas de relatório com o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="407c9-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="407c9-115">A criação e o gerenciamento de agendas compartilhadas também podem ser executados com o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="407c9-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="407c9-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="407c9-116">In This Section</span></span>  
  
-   [<span data-ttu-id="407c9-117">Conectar-se a um servidor de relatório no Management Studio</span><span class="sxs-lookup"><span data-stu-id="407c9-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="407c9-118">Definir propriedades do servidor de relatório &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="407c9-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="407c9-119">Criar, excluir ou modificar uma função &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="407c9-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="407c9-120">Excluir um item &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="407c9-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="407c9-121">Cancelar Trabalhos do Servidor de Relatório &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="407c9-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="407c9-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="407c9-122">See Also</span></span>  
 <span data-ttu-id="407c9-123">[Servidor de relatório na ajuda Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="407c9-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="407c9-124">Apresentando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="407c9-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
