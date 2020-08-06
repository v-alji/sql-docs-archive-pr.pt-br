---
title: MSSQLSERVER_21862 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680443"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="7de53-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="7de53-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="7de53-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7de53-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7de53-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7de53-104">Product Name</span></span>|<span data-ttu-id="7de53-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7de53-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7de53-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7de53-106">Event ID</span></span>|<span data-ttu-id="7de53-107">21862</span><span class="sxs-lookup"><span data-stu-id="7de53-107">21862</span></span>|  
|<span data-ttu-id="7de53-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7de53-108">Event Source</span></span>|<span data-ttu-id="7de53-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7de53-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7de53-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7de53-110">Component</span></span>|<span data-ttu-id="7de53-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7de53-111">SQLEngine</span></span>|  
|<span data-ttu-id="7de53-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7de53-112">Symbolic Name</span></span>|<span data-ttu-id="7de53-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="7de53-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="7de53-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7de53-114">Message Text</span></span>|<span data-ttu-id="7de53-115">As colunas FILESTREAM não podem ser publicadas em uma publicação com o uso de um método de sincronização de 'database snapshot' nem de 'database snapshot character'.</span><span class="sxs-lookup"><span data-stu-id="7de53-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7de53-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="7de53-116">Explanation</span></span>  
 <span data-ttu-id="7de53-117">Como os dados FILESTREAM não podem ser acessados por meio de um instantâneo de banco de dados, o Snapshot Agent não conseguirá ler os dados FILESTREAM quando o parâmetro *database snapshot* ou *database_snapshot_character* estiver especificado para o método de sincronização da publicação.</span><span class="sxs-lookup"><span data-stu-id="7de53-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7de53-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7de53-118">User Action</span></span>  
 <span data-ttu-id="7de53-119">Altere o método de sincronização da publicação para algo diferente de *database snapshot* ou *database_snapshot_character* ou apenas exclua a coluna FILESTREAM da publicação.</span><span class="sxs-lookup"><span data-stu-id="7de53-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
