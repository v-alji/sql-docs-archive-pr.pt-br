---
title: MSSQLSERVER_21889 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681664"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="27c5d-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="27c5d-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="27c5d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="27c5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27c5d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="27c5d-104">Product Name</span></span>|<span data-ttu-id="27c5d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="27c5d-105">SQL Server</span></span>|  
|<span data-ttu-id="27c5d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="27c5d-106">Event ID</span></span>|<span data-ttu-id="27c5d-107">21889</span><span class="sxs-lookup"><span data-stu-id="27c5d-107">21889</span></span>|  
|<span data-ttu-id="27c5d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="27c5d-108">Event Source</span></span>|<span data-ttu-id="27c5d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27c5d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27c5d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="27c5d-110">Component</span></span>|<span data-ttu-id="27c5d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="27c5d-111">SQLEngine</span></span>|  
|<span data-ttu-id="27c5d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="27c5d-112">Symbolic Name</span></span>|<span data-ttu-id="27c5d-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="27c5d-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="27c5d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="27c5d-114">Message Text</span></span>|<span data-ttu-id="27c5d-115">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] '% s' não é um publicador de replicação.</span><span class="sxs-lookup"><span data-stu-id="27c5d-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="27c5d-116">Execute `sp_adddistributor` na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] '%s' com o distribuidor '%s' para habilitar a instância para hospedar o banco de dados de publicação '%s'.</span><span class="sxs-lookup"><span data-stu-id="27c5d-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="27c5d-117">Certifique-se de especificar as mesmas informações de logon e senha que foram usadas para o publicador original.</span><span class="sxs-lookup"><span data-stu-id="27c5d-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27c5d-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="27c5d-118">Explanation</span></span>  
 <span data-ttu-id="27c5d-119">Para hospedar o banco de dados publicador, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser um publicador de replicação.</span><span class="sxs-lookup"><span data-stu-id="27c5d-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="27c5d-120">`sp_validate_redirected_publisher` chama `sp_helpdistributor` no servidor remoto para determinar se o servidor é um publicador de replicação.</span><span class="sxs-lookup"><span data-stu-id="27c5d-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="27c5d-121">Esse erro é retornado quando a execução do procedimento armazenado `sp_helpdistributor` indica que a instância de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é um publicador de replicação.</span><span class="sxs-lookup"><span data-stu-id="27c5d-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27c5d-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="27c5d-122">User Action</span></span>  
 <span data-ttu-id="27c5d-123">Execute `sp_adddistributor` na instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados publicador.</span><span class="sxs-lookup"><span data-stu-id="27c5d-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="27c5d-124">Ao executar `sp_adddistributor`, especifique o distribuidor correto.</span><span class="sxs-lookup"><span data-stu-id="27c5d-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="27c5d-125">Use o mesmo valor para o *@password* parâmetro que foi usado quando `sp_adddistributor` o foi executado inicialmente no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="27c5d-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
