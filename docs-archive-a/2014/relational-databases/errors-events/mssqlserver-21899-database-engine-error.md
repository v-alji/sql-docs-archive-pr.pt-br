---
title: MSSQLSERVER_21899 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680436"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="42379-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="42379-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="42379-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="42379-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42379-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="42379-104">Product Name</span></span>|<span data-ttu-id="42379-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42379-105">SQL Server</span></span>|  
|<span data-ttu-id="42379-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="42379-106">Event ID</span></span>|<span data-ttu-id="42379-107">21899</span><span class="sxs-lookup"><span data-stu-id="42379-107">21899</span></span>|  
|<span data-ttu-id="42379-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="42379-108">Event Source</span></span>|<span data-ttu-id="42379-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42379-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42379-110">Componente</span><span class="sxs-lookup"><span data-stu-id="42379-110">Component</span></span>|<span data-ttu-id="42379-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42379-111">SQLEngine</span></span>|  
|<span data-ttu-id="42379-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="42379-112">Symbolic Name</span></span>|<span data-ttu-id="42379-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="42379-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="42379-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="42379-114">Message Text</span></span>|<span data-ttu-id="42379-115">A consulta no publicador redirecionado '%s' para determinar se havia entradas de sysserver para os assinantes do publicador original '%s' falhou com o erro '%d', mensagem de erro '%s'.</span><span class="sxs-lookup"><span data-stu-id="42379-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42379-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="42379-116">Explanation</span></span>  
 <span data-ttu-id="42379-117">`sp_validate_redirected_publisher` consulta as tabelas de metadados de assinatura do banco de dados publicador no servidor remoto para determinar seus assinantes associados.</span><span class="sxs-lookup"><span data-stu-id="42379-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="42379-118">O erro 21899 será retornado se esta consulta falhar.</span><span class="sxs-lookup"><span data-stu-id="42379-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="42379-119">A consulta de validação requer acesso ao banco de dados publicado no publicador redirecionado.</span><span class="sxs-lookup"><span data-stu-id="42379-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="42379-120">Se o logon tiver especificado quando `sp_adddistpublisher` foi chamado, o publicador original não será autorizado a acessar o banco de dados publicado no publicador redirecionado; o erro 21899 será retornado.</span><span class="sxs-lookup"><span data-stu-id="42379-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42379-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="42379-121">User Action</span></span>  
 <span data-ttu-id="42379-122">Revise a mensagem de erro citada para determinar a causa da falha e execute a ação corretiva apropriada.</span><span class="sxs-lookup"><span data-stu-id="42379-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
