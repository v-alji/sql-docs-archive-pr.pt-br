---
title: Utilitário SqlLocalDB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678394"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="19def-102">Utilitário SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="19def-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="19def-103">Use o `SqlLocalDB` Utilitário para criar uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="19def-104">O `SqlLocalDB` utilitário (SqlLocalDB.exe) é uma ferramenta de linha de comando simples para permitir que usuários e desenvolvedores criem e gerenciem uma instância do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="19def-105">Para obter informações sobre como usar o **LocalDB**, consulte [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span><span class="sxs-lookup"><span data-stu-id="19def-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19def-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="19def-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="19def-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="19def-107">Arguments</span></span>  
 <span data-ttu-id="19def-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="19def-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="19def-109">Cria uma nova instância do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="19def-110">`SqlLocalDB`usa a versão de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binários especificada por *\<instance-version>* argumento.</span><span class="sxs-lookup"><span data-stu-id="19def-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="19def-111">O número da versão é especificado em formato numérico com pelo menos um decimal.</span><span class="sxs-lookup"><span data-stu-id="19def-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="19def-112">Os números de versões secundárias (pacotes de serviço) são opcionais.</span><span class="sxs-lookup"><span data-stu-id="19def-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="19def-113">Por exemplo, os dois números de versão seguintes são aceitáveis: 11.0 ou 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="19def-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="19def-114">A versão especificada deve ser estalada no computador.</span><span class="sxs-lookup"><span data-stu-id="19def-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="19def-115">Se não for especificado, o número de versão padrão será a versão do `SqlLocalDB` utilitário.</span><span class="sxs-lookup"><span data-stu-id="19def-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="19def-116">A adição de **-s** inicia a nova instância do **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="19def-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="19def-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="19def-118">Compartilha a instância privada especificada do **LocalDB** que usa o nome compartilhado especificado.</span><span class="sxs-lookup"><span data-stu-id="19def-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="19def-119">Se a SID ou o nome de conta do usuário for omitido, o valor padrão será o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="19def-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="19def-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="19def-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="19def-121">Interrompe o compartilhamento da instância especificada compartilhada do **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="19def-122">[ **delete** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="19def-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="19def-123">Exclui a instância especificada do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="19def-124">[ **start** | **s** ] " *\<instance-name>* "</span><span class="sxs-lookup"><span data-stu-id="19def-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="19def-125">Inicia a instância especificada do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="19def-126">Quando tem êxito, a instrução retorna o endereço de pipe nomeado do **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="19def-127">[ **stop** | **p** ] *\<instance-name>* [ **-i** ] [ **-k** ]</span><span class="sxs-lookup"><span data-stu-id="19def-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="19def-128">Interrompe a instância especificada do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="19def-129">Adicionar **-i** solicita o desligamento da instância com a `NOWAIT` opção.</span><span class="sxs-lookup"><span data-stu-id="19def-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="19def-130">A adição de **-k** elimina o processo da instância sem contatá-la.</span><span class="sxs-lookup"><span data-stu-id="19def-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="19def-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="19def-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="19def-132">Lista todas as instâncias do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** de propriedade do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="19def-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="19def-133">*\<instance-name>* retorna o nome, a versão, o estado (Em execução ou Parado), a hora da última inicialização da instância especificada do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB** e o nome do pipe local do **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="19def-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="19def-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="19def-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="19def-135">**trace on** habilita o rastreamento para as `SqlLocalDB` chamadas à API para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="19def-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="19def-136">**trace off** desabilita o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="19def-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="19def-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="19def-137">**-?**</span></span>  
 <span data-ttu-id="19def-138">Retorna descrições breves de cada `SqlLocalDB` opção.</span><span class="sxs-lookup"><span data-stu-id="19def-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19def-139">Comentários</span><span class="sxs-lookup"><span data-stu-id="19def-139">Remarks</span></span>  
 <span data-ttu-id="19def-140">O argumento *instance name* deve seguir as regras de identificadores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou deve ser colocado entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="19def-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="19def-141">A execução de SqlLocalDB sem argumentos retorna o texto da ajuda.</span><span class="sxs-lookup"><span data-stu-id="19def-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="19def-142">Operações diferentes de iniciar podem ser executados apenas em uma instância que pertence ao usuário conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="19def-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="19def-143">Exemplos</span><span class="sxs-lookup"><span data-stu-id="19def-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="19def-144">a.</span><span class="sxs-lookup"><span data-stu-id="19def-144">A.</span></span> <span data-ttu-id="19def-145">Criando uma instância do LocalDB</span><span class="sxs-lookup"><span data-stu-id="19def-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="19def-146">O exemplo a seguir cria uma instância do [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** denominada `DEPARTMENT` que usa os binários do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] e inicia a instância.</span><span class="sxs-lookup"><span data-stu-id="19def-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="19def-147">B.</span><span class="sxs-lookup"><span data-stu-id="19def-147">B.</span></span> <span data-ttu-id="19def-148">Trabalhando com uma instância compartilhada do LocalDB</span><span class="sxs-lookup"><span data-stu-id="19def-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="19def-149">Abrir um prompt de comando usando privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="19def-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="19def-150">Execute o código a seguir para conectar-se à instância compartilhada do **LocalDB** usando o logon `NewLogin` .</span><span class="sxs-lookup"><span data-stu-id="19def-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="19def-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19def-151">See Also</span></span>  
 [<span data-ttu-id="19def-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="19def-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
