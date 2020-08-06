---
title: MSSQLSERVER_4064 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582459"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="3c7eb-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="3c7eb-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="3c7eb-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3c7eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c7eb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3c7eb-104">Product Name</span></span>|<span data-ttu-id="3c7eb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c7eb-105">SQL Server</span></span>|  
|<span data-ttu-id="3c7eb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3c7eb-106">Event ID</span></span>|<span data-ttu-id="3c7eb-107">4064</span><span class="sxs-lookup"><span data-stu-id="3c7eb-107">4064</span></span>|  
|<span data-ttu-id="3c7eb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3c7eb-108">Event Source</span></span>|<span data-ttu-id="3c7eb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c7eb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c7eb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3c7eb-110">Component</span></span>|<span data-ttu-id="3c7eb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c7eb-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c7eb-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3c7eb-112">Symbolic Name</span></span>|<span data-ttu-id="3c7eb-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="3c7eb-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="3c7eb-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3c7eb-114">Message Text</span></span>|<span data-ttu-id="3c7eb-115">Não é possível abrir o banco de dados padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-115">Cannot open user default database.</span></span> <span data-ttu-id="3c7eb-116">Falha no logon.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c7eb-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="3c7eb-117">Explanation</span></span>  
 <span data-ttu-id="3c7eb-118">O logon do SQL Server não pôde se conectar devido a um problema com o banco de dados padrão.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="3c7eb-119">O próprio banco de dados é inválido ou o logon não tem a permissão CONNECT no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c7eb-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3c7eb-120">User Action</span></span>  
 <span data-ttu-id="3c7eb-121">Use ALTER LOGIN para alterar o banco de dados padrão do logon.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="3c7eb-122">Conceda a permissão CONNECT para o logon.</span><span class="sxs-lookup"><span data-stu-id="3c7eb-122">Grant CONNECT permission to the login.</span></span>  
  
  
