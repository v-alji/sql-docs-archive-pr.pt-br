---
title: MSSQLSERVER_1803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1803 (Database Engine error)
ms.assetid: d4315390-82f1-4c4c-8d1b-1a4989537cca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11302f882846c49c6e9998608967e7042ac9860c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575157"
---
# <a name="mssqlserver_1803"></a><span data-ttu-id="7348c-102">MSSQLSERVER_1803</span><span class="sxs-lookup"><span data-stu-id="7348c-102">MSSQLSERVER_1803</span></span>
    
## <a name="details"></a><span data-ttu-id="7348c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7348c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7348c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7348c-104">Product Name</span></span>|<span data-ttu-id="7348c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7348c-105">SQL Server</span></span>|  
|<span data-ttu-id="7348c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7348c-106">Event ID</span></span>|<span data-ttu-id="7348c-107">1803</span><span class="sxs-lookup"><span data-stu-id="7348c-107">1803</span></span>|  
|<span data-ttu-id="7348c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7348c-108">Event Source</span></span>|<span data-ttu-id="7348c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7348c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7348c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7348c-110">Component</span></span>|<span data-ttu-id="7348c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7348c-111">SQLEngine</span></span>|  
|<span data-ttu-id="7348c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7348c-112">Symbolic Name</span></span>|<span data-ttu-id="7348c-113">NO_SPACE</span><span class="sxs-lookup"><span data-stu-id="7348c-113">NO_SPACE</span></span>|  
|<span data-ttu-id="7348c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7348c-114">Message Text</span></span>|<span data-ttu-id="7348c-115">Falha em CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7348c-115">CREATE DATABASE failed.</span></span> <span data-ttu-id="7348c-116">O arquivo primário deve ter pelo menos %d MB para acomodar uma cópia do modelo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7348c-116">Primary file must be at least %d MB to accommodate a copy of the model database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7348c-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="7348c-117">Explanation</span></span>  
 <span data-ttu-id="7348c-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cria um banco de dados fazendo uma cópia do banco de dados modelo.</span><span class="sxs-lookup"><span data-stu-id="7348c-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a database by making a copy of the model database.</span></span> <span data-ttu-id="7348c-119">Em seguida, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renomeia a cópia e aumenta o novo banco de dados para o tamanho solicitado.</span><span class="sxs-lookup"><span data-stu-id="7348c-119">Then [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renames the copy, and enlarges the new database to the requested size.</span></span> <span data-ttu-id="7348c-120">Nesse caso, o usuário tentou criar um banco de dados menor que o banco de dados modelo.</span><span class="sxs-lookup"><span data-stu-id="7348c-120">In this case, the user tried to create a database smaller than the model database.</span></span> <span data-ttu-id="7348c-121">A operação falhou porque a cópia do banco de dados modelo não caberia no arquivo de dados principal, já que o arquivo era menor que o banco de dados modelo.</span><span class="sxs-lookup"><span data-stu-id="7348c-121">The operation failed because the copy of the model database could not fit on the primary data file, because the file was smaller than the model database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7348c-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7348c-122">User Action</span></span>  
 <span data-ttu-id="7348c-123">Crie o banco de dados usando um tamanho de arquivo de banco de dados maior.</span><span class="sxs-lookup"><span data-stu-id="7348c-123">Create the database by using a larger database file size.</span></span> <span data-ttu-id="7348c-124">Em seguida, reduza o banco de dados se desejar usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou a instrução DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="7348c-124">Then shrink the database if you want by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or the DBCC SHRINKDATABASE statement.</span></span>  
  
  
