---
title: LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 626b73d3-a257-4b45-82fb-c6299faa0001
author: stevestein
ms.author: sstein
ms.openlocfilehash: b127bedb0dc13c0b8b5a238a8ef104ca9a00bd85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576415"
---
# <a name="localdb_error_cannot_create_instance_folder"></a><span data-ttu-id="64309-102">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="64309-102">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>
    
## <a name="details"></a><span data-ttu-id="64309-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="64309-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64309-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="64309-104">Product Name</span></span>|<span data-ttu-id="64309-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="64309-105">SQL Server</span></span>|  
|<span data-ttu-id="64309-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="64309-106">Event ID</span></span>|<span data-ttu-id="64309-107">256</span><span class="sxs-lookup"><span data-stu-id="64309-107">256</span></span>|  
|<span data-ttu-id="64309-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="64309-108">Event Source</span></span>|<span data-ttu-id="64309-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="64309-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="64309-110">Componente</span><span class="sxs-lookup"><span data-stu-id="64309-110">Component</span></span>|<span data-ttu-id="64309-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="64309-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="64309-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="64309-112">Message Text</span></span>|<span data-ttu-id="64309-113">Não é possível criar a pasta para a instância do banco de dados local em:%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server local DB\Instances \\<nome da instância \> .</span><span class="sxs-lookup"><span data-stu-id="64309-113">Cannot create folder for the Local Database instance at: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64309-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="64309-114">Explanation</span></span>  
 <span data-ttu-id="64309-115">Uma pasta não pode ser criada abaixo de %userprofile%.</span><span class="sxs-lookup"><span data-stu-id="64309-115">A folder cannot be created under %userprofile%.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64309-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="64309-116">User Action</span></span>  
  
