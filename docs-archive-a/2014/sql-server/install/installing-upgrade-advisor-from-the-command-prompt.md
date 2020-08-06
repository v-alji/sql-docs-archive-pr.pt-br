---
title: Instalando o supervisor de atualização no prompt de comando | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679638"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="9b3db-102">Instalando o Supervisor de Atualização do prompt de comando</span><span class="sxs-lookup"><span data-stu-id="9b3db-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="9b3db-103">Você pode instalar o Supervisor de Atualização usando o Assistente de Instalação ou a partir do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9b3db-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="9b3db-104">Usando o prompt de comando, você poderá executar instalações autônomas e automatizadas.</span><span class="sxs-lookup"><span data-stu-id="9b3db-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="9b3db-105">Sintaxe de instalação</span><span class="sxs-lookup"><span data-stu-id="9b3db-105">Installation Syntax</span></span>  
 <span data-ttu-id="9b3db-106">A sintaxe básica por instalar o Supervisor de Atualização a partir do prompt de comando é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b3db-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="9b3db-107">A tabela a seguir mostra as opções mais comuns.</span><span class="sxs-lookup"><span data-stu-id="9b3db-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="9b3db-108">Argumento</span><span class="sxs-lookup"><span data-stu-id="9b3db-108">Argument</span></span>|<span data-ttu-id="9b3db-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b3db-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9b3db-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="9b3db-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="9b3db-111">Define nível de interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="9b3db-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="9b3db-112">n = nenhuma interface do usuário</span><span class="sxs-lookup"><span data-stu-id="9b3db-112">n = no UI</span></span><br /><br /> <span data-ttu-id="9b3db-113">b = interface do usuário básica (apenas progresso, nenhum prompt)</span><span class="sxs-lookup"><span data-stu-id="9b3db-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="9b3db-114">r = interface do usuário reduzida (caixa de diálogo ao término da instalação)</span><span class="sxs-lookup"><span data-stu-id="9b3db-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="9b3db-115">f = interface do usuário completa</span><span class="sxs-lookup"><span data-stu-id="9b3db-115">f = full UI</span></span>|  
|<span data-ttu-id="9b3db-116">/L</span><span class="sxs-lookup"><span data-stu-id="9b3db-116">/L</span></span>|<span data-ttu-id="9b3db-117">Especifica as opções do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="9b3db-117">Specifies log file options.</span></span> <span data-ttu-id="9b3db-118">Para registrar todas as mensagens no *log_file_name*, use **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="9b3db-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="9b3db-119">Para registrar somente mensagens de erro, use `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="9b3db-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="9b3db-120">ADDLOCAL = TODOS OS&#124; REMOVER = TODOS OS&#124;REINSTALAR = TODOS</span><span class="sxs-lookup"><span data-stu-id="9b3db-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="9b3db-121">Especifica a instalação (ADDLOCAL), remoção (REMOVE) ou reinstalação (REINSTALL) do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="9b3db-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="9b3db-122">UAINSTALLDIR=path</span><span class="sxs-lookup"><span data-stu-id="9b3db-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="9b3db-123">Instala o Supervisor de Atualização no local especificado pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="9b3db-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="9b3db-124">Exemplos de instalação</span><span class="sxs-lookup"><span data-stu-id="9b3db-124">Installation Examples</span></span>  
 <span data-ttu-id="9b3db-125">O exemplo a seguir mostra como instalar o Supervisor de Atualização usando o prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9b3db-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="9b3db-126">Você também pode usar o programa Msiexec quando executar este comando:</span><span class="sxs-lookup"><span data-stu-id="9b3db-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="9b3db-127">Isso poderá ser útil se você tiver que usar opções de instalação adicionais.</span><span class="sxs-lookup"><span data-stu-id="9b3db-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="9b3db-128">Exemplos de remoção</span><span class="sxs-lookup"><span data-stu-id="9b3db-128">Removal Examples</span></span>  
 <span data-ttu-id="9b3db-129">O exemplo a seguir mostra como remover o Supervisor de Atualização usando o prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9b3db-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="9b3db-130">Você também pode usar o programa Msiexec quando executar este comando:</span><span class="sxs-lookup"><span data-stu-id="9b3db-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b3db-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b3db-131">See Also</span></span>  
 <span data-ttu-id="9b3db-132">[Instalando o supervisor de atualização](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="9b3db-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="9b3db-133">Pré-requisitos do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="9b3db-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
