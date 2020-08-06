---
title: Conectar-se ao Mecanismo de Banco de Dados com sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570594"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="7e30c-102">Conectar-se ao Mecanismo de Banco de Dados com sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7e30c-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7e30c-103">dá suporte à comunicação de cliente com o protocolo de rede TCP/IP (padrão) e o protocolo de pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="7e30c-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="7e30c-104">O protocolo de memória compartilhada também estará disponível se o cliente estiver se conectando a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="7e30c-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="7e30c-105">Há três métodos comuns de selecionar o protocolo.</span><span class="sxs-lookup"><span data-stu-id="7e30c-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="7e30c-106">O protocolo usado pelo utilitário **sqlcmd** é determinado na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="7e30c-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="7e30c-107">O**sqlcmd** usa o protocolo especificado como parte da cadeia de conexão, conforme a descrição abaixo.</span><span class="sxs-lookup"><span data-stu-id="7e30c-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="7e30c-108">Se nenhum protocolo for especificado como parte da cadeia de conexão, o **sqlcmd** usará o protocolo definido como parte do alias ao qual ele está se conectando.</span><span class="sxs-lookup"><span data-stu-id="7e30c-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="7e30c-109">Para configurar **sqlcmd** para usar um protocolo de rede específico criando um alias, veja [Criar ou excluir um alias de servidor para ser usado por um cliente &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="7e30c-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="7e30c-110">Se o protocolo não for especificado de outra forma, o **sqlcmd** usará o protocolo de rede determinado pela ordem de protocolos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7e30c-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="7e30c-111">Os exemplos a seguir mostram várias formas de fazer a conexão com a instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)] na porta 1433, presumindo-se que as instâncias nomeadas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] estejam escutando na porta 1691.</span><span class="sxs-lookup"><span data-stu-id="7e30c-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="7e30c-112">Alguns dos exemplos usam o endereço IP do adaptador de loopback (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="7e30c-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="7e30c-113">Experimente usar o endereço IP da placa de interface de rede de seu computador.</span><span class="sxs-lookup"><span data-stu-id="7e30c-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="7e30c-114">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando o nome da instância:</span><span class="sxs-lookup"><span data-stu-id="7e30c-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="7e30c-115">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando o endereço IP:</span><span class="sxs-lookup"><span data-stu-id="7e30c-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="7e30c-116">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] especificando o número da porta de TCP\IP:</span><span class="sxs-lookup"><span data-stu-id="7e30c-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="7e30c-117">Para fazer a conexão usando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="7e30c-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="7e30c-118">Conecte-se usando a seguinte sintaxe geral:</span><span class="sxs-lookup"><span data-stu-id="7e30c-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="7e30c-119">Conecte-se à instância padrão:</span><span class="sxs-lookup"><span data-stu-id="7e30c-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="7e30c-120">Conecte-se a uma instância nomeada:</span><span class="sxs-lookup"><span data-stu-id="7e30c-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="7e30c-121">Para fazer a conexão usando pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="7e30c-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="7e30c-122">Conecte-se usando uma das seguintes sintaxes gerais:</span><span class="sxs-lookup"><span data-stu-id="7e30c-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="7e30c-123">Conecte-se à instância padrão:</span><span class="sxs-lookup"><span data-stu-id="7e30c-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="7e30c-124">Conecte-se a uma instância nomeada:</span><span class="sxs-lookup"><span data-stu-id="7e30c-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="7e30c-125">Para fazer a conexão usando memória compartilhada (uma chamada de procedimento local) a partir de um cliente no servidor</span><span class="sxs-lookup"><span data-stu-id="7e30c-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="7e30c-126">Conecte-se usando uma das seguintes sintaxes gerais:</span><span class="sxs-lookup"><span data-stu-id="7e30c-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="7e30c-127">Conecte-se à instância padrão:</span><span class="sxs-lookup"><span data-stu-id="7e30c-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="7e30c-128">Conecte-se a uma instância nomeada:</span><span class="sxs-lookup"><span data-stu-id="7e30c-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
