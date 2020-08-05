---
title: MSSQLSERVER_945 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573042"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="ba697-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="ba697-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="ba697-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba697-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba697-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ba697-104">Product Name</span></span>|<span data-ttu-id="ba697-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba697-105">SQL Server</span></span>|  
|<span data-ttu-id="ba697-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ba697-106">Event ID</span></span>|<span data-ttu-id="ba697-107">945</span><span class="sxs-lookup"><span data-stu-id="ba697-107">945</span></span>|  
|<span data-ttu-id="ba697-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ba697-108">Event Source</span></span>|<span data-ttu-id="ba697-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ba697-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ba697-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ba697-110">Component</span></span>|<span data-ttu-id="ba697-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ba697-111">SQLEngine</span></span>|  
|<span data-ttu-id="ba697-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ba697-112">Symbolic Name</span></span>|<span data-ttu-id="ba697-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="ba697-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="ba697-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ba697-114">Message Text</span></span>|<span data-ttu-id="ba697-115">O banco de dados '%.\*ls' não pode ser aberto devido a arquivos inacessíveis, memória ou espaço em disco insuficiente.</span><span class="sxs-lookup"><span data-stu-id="ba697-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="ba697-116">Consulte o log de erros do SQL Server para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ba697-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ba697-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="ba697-117">Explanation</span></span>  
 <span data-ttu-id="ba697-118">O banco de dados não pôde ser acessado porque faltam arquivos ou outros recursos.</span><span class="sxs-lookup"><span data-stu-id="ba697-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba697-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ba697-119">User Action</span></span>  
 <span data-ttu-id="ba697-120">Verifique o log de erros para obter informações adicionais sobre memória, espaço em disco ou falha de permissão.</span><span class="sxs-lookup"><span data-stu-id="ba697-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="ba697-121">Confirme o local dos arquivos .mdf e .ndf do banco de dados afetado e confirme se a conta usada pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)] tem permissão para acessar esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="ba697-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="ba697-122">Depois de corrigir o problema, reinicialize o banco de dados usando ALTER DATABASE para defini-lo como ONLINE.</span><span class="sxs-lookup"><span data-stu-id="ba697-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
