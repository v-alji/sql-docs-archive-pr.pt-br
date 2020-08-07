---
title: Compreender a propriedade do diagrama de banco de dados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682036"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="838ec-102">Compreender a propriedade do diagrama de banco de dados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="838ec-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="838ec-103">Para usar o Designer de Diagrama de Banco de Dados, ele precisa ser configurado primeiramente por um membro da função db_owner (função de bancos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) para controle do acesso a diagramas.</span><span class="sxs-lookup"><span data-stu-id="838ec-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="838ec-104">Cada diagrama tem um e apenas um proprietário, o usuário que o criou.</span><span class="sxs-lookup"><span data-stu-id="838ec-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="838ec-105">Para obter mais informações sobre como configurar a diagramação, consulte [Configurar o designer de diagrama de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="838ec-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="838ec-106">Pontos de destaque sobre propriedade de diagrama:</span><span class="sxs-lookup"><span data-stu-id="838ec-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="838ec-107">Embora qualquer usuário com acesso a um banco de dados possa criar um diagrama, depois de criado, os únicos usuários que podem exibi-lo são o designer do diagrama e os membros da função db_owner.</span><span class="sxs-lookup"><span data-stu-id="838ec-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="838ec-108">A propriedade de diagramas só pode ser transferida para membros da função db_owner.</span><span class="sxs-lookup"><span data-stu-id="838ec-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="838ec-109">Isso é possível apenas depois que o proprietário anterior do diagrama tiver sido removido do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="838ec-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="838ec-110">Se o proprietário de um diagrama for removido do banco de dados, o diagrama permanecerá no banco de dados até que um membro da função db_owner tente abri-lo.</span><span class="sxs-lookup"><span data-stu-id="838ec-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="838ec-111">Nesse momento, o membro db_owner pode assumir a propriedade do diagrama.</span><span class="sxs-lookup"><span data-stu-id="838ec-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838ec-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="838ec-112">See Also</span></span>  
 <span data-ttu-id="838ec-113">[Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="838ec-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="838ec-114">Configurar o Designer de Diagramas de Banco de Dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="838ec-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
