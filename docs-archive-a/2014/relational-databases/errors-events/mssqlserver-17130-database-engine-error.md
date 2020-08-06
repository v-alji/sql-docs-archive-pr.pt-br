---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680454"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="5b5e3-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="5b5e3-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="5b5e3-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5b5e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b5e3-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5b5e3-104">Product Name</span></span>|<span data-ttu-id="5b5e3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b5e3-105">SQL Server</span></span>|  
|<span data-ttu-id="5b5e3-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5b5e3-106">Event ID</span></span>|<span data-ttu-id="5b5e3-107">17130</span><span class="sxs-lookup"><span data-stu-id="5b5e3-107">17130</span></span>|  
|<span data-ttu-id="5b5e3-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5b5e3-108">Event Source</span></span>|<span data-ttu-id="5b5e3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b5e3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b5e3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5b5e3-110">Component</span></span>|<span data-ttu-id="5b5e3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b5e3-111">SQLEngine</span></span>|  
|<span data-ttu-id="5b5e3-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5b5e3-112">Symbolic Name</span></span>|<span data-ttu-id="5b5e3-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="5b5e3-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="5b5e3-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5b5e3-114">Message Text</span></span>|<span data-ttu-id="5b5e3-115">Não há memória suficiente para o número de bloqueios configurado.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="5b5e3-116">Tente começar com uma tabela de hash de bloqueio menor, que pode causar impacto no desempenho.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="5b5e3-117">Contate o administrador de banco de dados para configurar mais memória para a instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b5e3-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="5b5e3-118">Explanation</span></span>  
 <span data-ttu-id="5b5e3-119">Não há memória suficiente para o tamanho da tabela de hash do gerenciador de bloqueios desejado.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="5b5e3-120">Ocorrerá uma tentativa para alocar uma tabela de hash menor.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b5e3-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5b5e3-121">User Action</span></span>  
 <span data-ttu-id="5b5e3-122">Verifique os parâmetros de configuração da memória do servidor (min/max server memory) e verifique se há pressões de memória.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="5b5e3-123">Forneça mais memória ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b5e3-123">Provide SQL Server more memory.</span></span>  
  
  
