---
title: Opção de cancelamento (ferramenta de administração do Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574961"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="3223e-102">Opção de cancelamento (ferramenta de administração do Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="3223e-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="3223e-103">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ferramenta de administração de Distributed Replay, `DReplay.exe` , é uma ferramenta de linha de comando que você pode usar para se comunicar com o Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="3223e-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="3223e-104">Este tópico descreve a opção de linha de comando **cancel** e a sintaxe correspondente.</span><span class="sxs-lookup"><span data-stu-id="3223e-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="3223e-105">A opção **cancel** cancela a operação atual que está em execução no controlador.</span><span class="sxs-lookup"><span data-stu-id="3223e-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="3223e-106">![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3223e-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="3223e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3223e-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="3223e-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3223e-108">Parameters</span></span>
 <span data-ttu-id="3223e-109">**-m** *controlador* o nome do computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="3223e-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="3223e-110">Você pode usar "`localhost`" ou "`.`" para fazer referência ao computador local.</span><span class="sxs-lookup"><span data-stu-id="3223e-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="3223e-111">Se o parâmetro **-m** não for especificado, será usado o computador local.</span><span class="sxs-lookup"><span data-stu-id="3223e-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="3223e-112">**-q** Modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="3223e-112">**-q** Quiet mode.</span></span> <span data-ttu-id="3223e-113">Não solicita confirmação.</span><span class="sxs-lookup"><span data-stu-id="3223e-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="3223e-114">O parâmetro **-q** é opcional.</span><span class="sxs-lookup"><span data-stu-id="3223e-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="3223e-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3223e-115">Examples</span></span>
 <span data-ttu-id="3223e-116">No exemplo a seguir, uma solicitação de cancelamento é enviada no modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="3223e-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="3223e-117">O valor `localhost` indica que o serviço do controlador está em execução no mesmo computador que a ferramenta de administração.</span><span class="sxs-lookup"><span data-stu-id="3223e-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="3223e-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="3223e-118">Permissions</span></span>
 <span data-ttu-id="3223e-119">Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="3223e-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="3223e-120">Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="3223e-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="3223e-121">Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="3223e-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3223e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3223e-122">See Also</span></span>
 [<span data-ttu-id="3223e-123">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="3223e-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


