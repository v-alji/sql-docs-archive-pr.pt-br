---
title: Opção de configuração de servidor remote admin connections | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582121"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="e91e9-102">Opção de configuração de servidor remote admin connections</span><span class="sxs-lookup"><span data-stu-id="e91e9-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e91e9-103">fornece uma DAC (conexão de administrador dedicada).</span><span class="sxs-lookup"><span data-stu-id="e91e9-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="e91e9-104">A DAC permite que um administrador acesse um servidor em execução para desempenhar funções de diagnóstico ou executar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , ou para solucionar problemas no servidor, mesmo quando o servidor está bloqueado ou está sendo executado em um estado anormal e não está respondendo a uma conexão com o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e91e9-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="e91e9-105">Por padrão, a DAC só está disponível a partir de um cliente no servidor.</span><span class="sxs-lookup"><span data-stu-id="e91e9-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="e91e9-106">Para permitir que os aplicativos cliente de computadores remotos utilizem a DAC, use a opção remote admin connections sp_configure.</span><span class="sxs-lookup"><span data-stu-id="e91e9-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="e91e9-107">Por padrão, a DAC escuta apenas no endereço IP de loopback (127.0.0.1), porta 1434.</span><span class="sxs-lookup"><span data-stu-id="e91e9-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="e91e9-108">Se a porta TCP 1434 não estiver disponível, uma porta TCP será atribuída dinamicamente quando o [!INCLUDE[ssDE](../../includes/ssde-md.md)] for iniciado.</span><span class="sxs-lookup"><span data-stu-id="e91e9-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="e91e9-109">Quando houver mais de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada em um computador, verifique o número da porta TCP no log de erros.</span><span class="sxs-lookup"><span data-stu-id="e91e9-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="e91e9-110">A tabela a seguir lista os possíveis valores para a opção remote admin connections.</span><span class="sxs-lookup"><span data-stu-id="e91e9-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="e91e9-111">Valor</span><span class="sxs-lookup"><span data-stu-id="e91e9-111">Value</span></span>|<span data-ttu-id="e91e9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e91e9-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e91e9-113">0</span><span class="sxs-lookup"><span data-stu-id="e91e9-113">0</span></span>|<span data-ttu-id="e91e9-114">Indica que apenas conexões locais são permitidas usando a DAC.</span><span class="sxs-lookup"><span data-stu-id="e91e9-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="e91e9-115">1</span><span class="sxs-lookup"><span data-stu-id="e91e9-115">1</span></span>|<span data-ttu-id="e91e9-116">Indica que são permitidas conexões remotas usando a DAC.</span><span class="sxs-lookup"><span data-stu-id="e91e9-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e91e9-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e91e9-117">Example</span></span>  
 <span data-ttu-id="e91e9-118">O exemplo a seguir habilita a DAC a partir de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e91e9-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e91e9-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e91e9-119">See Also</span></span>  
 [<span data-ttu-id="e91e9-120">Conexão de diagnóstico para administradores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="e91e9-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
