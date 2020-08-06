---
title: MSSQLSERVER_21898 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680438"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="34333-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="34333-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="34333-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="34333-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34333-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="34333-104">Product Name</span></span>|<span data-ttu-id="34333-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="34333-105">SQL Server</span></span>|  
|<span data-ttu-id="34333-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34333-106">Event ID</span></span>|<span data-ttu-id="34333-107">21898</span><span class="sxs-lookup"><span data-stu-id="34333-107">21898</span></span>|  
|<span data-ttu-id="34333-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="34333-108">Event Source</span></span>|<span data-ttu-id="34333-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="34333-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="34333-110">Componente</span><span class="sxs-lookup"><span data-stu-id="34333-110">Component</span></span>|<span data-ttu-id="34333-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34333-111">SQLEngine</span></span>|  
|<span data-ttu-id="34333-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="34333-112">Symbolic Name</span></span>|<span data-ttu-id="34333-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="34333-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="34333-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="34333-114">Message Text</span></span>|<span data-ttu-id="34333-115">O publicador '%s' usa o banco de dados de distribuição '%s', e não '%s', que é necessário para hospedar o banco de dados de publicação '%s'.</span><span class="sxs-lookup"><span data-stu-id="34333-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="34333-116">Execute `sp_changedistpublisher` no distribuidor '%s' para alterar o banco de dados de distribuição usado pelo publicador para '%s'.</span><span class="sxs-lookup"><span data-stu-id="34333-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34333-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="34333-117">Explanation</span></span>  
 <span data-ttu-id="34333-118">`sp_validate_redirected_publisher` consulta msdb.dbo.MSdistpublishers no distribuidor local para verificar se o banco de dados de distribuição usado pelo novo publicador é igual ao banco de dados de distribuição usado pelo publicador original.</span><span class="sxs-lookup"><span data-stu-id="34333-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="34333-119">Este erro é retornado quando esses bancos de dados são diferentes, tornando o publicador um host inadequado para o banco de dados publicador.</span><span class="sxs-lookup"><span data-stu-id="34333-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34333-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="34333-120">User Action</span></span>  
 <span data-ttu-id="34333-121">Execute o procedimento armazenado `sp_changedistpublisher` para alterar o banco de dados de distribuição do novo publicador para o utilizado pelo publicador original.</span><span class="sxs-lookup"><span data-stu-id="34333-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34333-122">A execução de `sp_changedistpublisher` tratará o problema se o banco de dados de distribuição incorreto tiver sido inserido quando `sp_adddistpublisher` foi executado no distribuidor do publicador.</span><span class="sxs-lookup"><span data-stu-id="34333-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="34333-123">No entanto, se o publicador remoto tiver publicações existentes de outro banco de dados de publicação que utilizam o banco de dados de distribuição identificado, essa alteração não será apropriada.</span><span class="sxs-lookup"><span data-stu-id="34333-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="34333-124">A replicação que usa o banco de dados de distribuição nomeado precisa ser removida sistematicamente e restabelecida através do banco de dados de distribuição do editor original para que o novo editor funcione como um host satisfatório.</span><span class="sxs-lookup"><span data-stu-id="34333-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
