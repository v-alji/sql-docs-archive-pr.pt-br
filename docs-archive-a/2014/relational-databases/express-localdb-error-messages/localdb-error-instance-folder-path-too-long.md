---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583077"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="a3336-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="a3336-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="a3336-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a3336-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3336-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a3336-104">Product Name</span></span>|<span data-ttu-id="a3336-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3336-105">SQL Server</span></span>|  
|<span data-ttu-id="a3336-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a3336-106">Event ID</span></span>|<span data-ttu-id="a3336-107">260</span><span class="sxs-lookup"><span data-stu-id="a3336-107">260</span></span>|  
|<span data-ttu-id="a3336-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a3336-108">Event Source</span></span>|<span data-ttu-id="a3336-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="a3336-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="a3336-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3336-110">Component</span></span>|<span data-ttu-id="a3336-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="a3336-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="a3336-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a3336-112">Message Text</span></span>|<span data-ttu-id="a3336-113">O comprimento do caminho completo da pasta da instância do Banco de Dados Local é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="a3336-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="a3336-114">A instância deve ser armazenada na pasta:%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server local DB\Instances \\<nome da instância \> .</span><span class="sxs-lookup"><span data-stu-id="a3336-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3336-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="a3336-115">Explanation</span></span>  
 <span data-ttu-id="a3336-116">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="a3336-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3336-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a3336-117">User Action</span></span>  
 <span data-ttu-id="a3336-118">Crie um novo caminho mais curto que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="a3336-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
