---
title: MSSQLSERVER_15661 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568608"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="fa31f-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="fa31f-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="fa31f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fa31f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa31f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="fa31f-104">Product Name</span></span>|<span data-ttu-id="fa31f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa31f-105">SQL Server</span></span>|  
|<span data-ttu-id="fa31f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fa31f-106">Event ID</span></span>|<span data-ttu-id="fa31f-107">15661</span><span class="sxs-lookup"><span data-stu-id="fa31f-107">15661</span></span>|  
|<span data-ttu-id="fa31f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="fa31f-108">Event Source</span></span>|<span data-ttu-id="fa31f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fa31f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fa31f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fa31f-110">Component</span></span>|<span data-ttu-id="fa31f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fa31f-111">SQLEngine</span></span>|  
|<span data-ttu-id="fa31f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="fa31f-112">Symbolic Name</span></span>|<span data-ttu-id="fa31f-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="fa31f-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="fa31f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fa31f-114">Message Text</span></span>|<span data-ttu-id="fa31f-115">O procedimento armazenado sp_estimate_data_compression_savings não pode ser usado para tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="fa31f-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa31f-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="fa31f-116">Explanation</span></span>  
 <span data-ttu-id="fa31f-117">Uma tabela temporária foi usada como um argumento para o procedimento armazenado sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="fa31f-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="fa31f-118">Embora a compactação de tabelas temporárias tenha suporte, não é possível usar sp_estimate_data_compression_savings para calcular as economias de compactação.</span><span class="sxs-lookup"><span data-stu-id="fa31f-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa31f-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fa31f-119">User Action</span></span>  
 <span data-ttu-id="fa31f-120">Remova a tabela temporária como um argumento para sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="fa31f-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
