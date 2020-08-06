---
title: Opção de status (ferramenta de administração do Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678456"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="e4a24-102">Opção de status (ferramenta de administração do Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="e4a24-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="e4a24-103">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ferramenta de administração de Distributed Replay, `DReplay.exe` , é uma ferramenta de linha de comando que você pode usar para se comunicar com o Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="e4a24-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="e4a24-104">Este tópico descreve a opção de linha de comando **status** e a sintaxe correspondente.</span><span class="sxs-lookup"><span data-stu-id="e4a24-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="e4a24-105">A opção **status** consulta o controlador e exibe o status atual.</span><span class="sxs-lookup"><span data-stu-id="e4a24-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="e4a24-106">![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4a24-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="e4a24-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e4a24-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="e4a24-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e4a24-108">Parameters</span></span>
 <span data-ttu-id="e4a24-109">**-m** *Controller* especifica o nome do computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="e4a24-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="e4a24-110">Você pode usar "`localhost`" ou "`.`" para fazer referência ao computador local.</span><span class="sxs-lookup"><span data-stu-id="e4a24-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="e4a24-111">Se o parâmetro **-m** não for especificado, será usado o computador local.</span><span class="sxs-lookup"><span data-stu-id="e4a24-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="e4a24-112">**-f** *status_interval* especifica a frequência (em segundos) na qual o status será exibido.</span><span class="sxs-lookup"><span data-stu-id="e4a24-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="e4a24-113">Se o parâmetro **-f** não for especificado, o intervalo padrão será de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="e4a24-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="e4a24-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e4a24-114">Examples</span></span>
 <span data-ttu-id="e4a24-115">No exemplo a seguir, o status atual é exibido a cada 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="e4a24-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="e4a24-116">O valor `localhost` indica que o serviço do controlador está em execução no mesmo computador que a ferramenta de administração.</span><span class="sxs-lookup"><span data-stu-id="e4a24-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="e4a24-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="e4a24-117">Permissions</span></span>
 <span data-ttu-id="e4a24-118">Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="e4a24-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="e4a24-119">Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="e4a24-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="e4a24-120">Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="e4a24-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4a24-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4a24-121">See Also</span></span>
 <span data-ttu-id="e4a24-122">[Depurador do Transact-SQL de](../../relational-databases/scripting/transact-sql-debugger.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="e4a24-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


