---
title: Propriedades de pipes nomeados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573340"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="112c4-102">Propriedades de Pipes Nomeados</span><span class="sxs-lookup"><span data-stu-id="112c4-102">Named Pipes Properties</span></span>
  <span data-ttu-id="112c4-103">Use a página **Protocolo**na caixa de diálogo **Propriedades de Pipes Nomeados** para exibir ou alterar o pipe nomeado que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta ao usar o protocolo Pipes Nomeados.</span><span class="sxs-lookup"><span data-stu-id="112c4-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="112c4-104">deve ser reiniciado para habilitar ou desabilitar o protocolo, ou para alterar o pipe nomeado.</span><span class="sxs-lookup"><span data-stu-id="112c4-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="112c4-105">Opções</span><span class="sxs-lookup"><span data-stu-id="112c4-105">Options</span></span>  
 <span data-ttu-id="112c4-106">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="112c4-106">**Enabled**</span></span>  
 <span data-ttu-id="112c4-107">Os valores possíveis são **Sim** e **Não**.</span><span class="sxs-lookup"><span data-stu-id="112c4-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="112c4-108">**Nome do Pipe**</span><span class="sxs-lookup"><span data-stu-id="112c4-108">**Pipe Name**</span></span>  
 <span data-ttu-id="112c4-109">Especifica o pipe nomeado no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta.</span><span class="sxs-lookup"><span data-stu-id="112c4-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="112c4-110">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta em: `\\.\pipe\sql\query` para a instância padrão e `\\.\pipe\MSSQL$<instancename>\sql\query` para uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="112c4-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="112c4-111">Este campo é limitado a 2.047 caracteres.</span><span class="sxs-lookup"><span data-stu-id="112c4-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="112c4-112">Criando um pipe nomeado alternativo</span><span class="sxs-lookup"><span data-stu-id="112c4-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="112c4-113">Para alterar o pipe nomeado, digite o nome do novo pipe na caixa **Nome do Pipe** e, em seguida, pare e reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="112c4-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="112c4-114">Como **sql\query** é bem conhecido como o pipe nomeado usado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a alteração do pipe pode ajudar a reduzir o risco de ataque de programas mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="112c4-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="112c4-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="112c4-115">Example</span></span>  
 <span data-ttu-id="112c4-116">Digite **\\\\.\pipe\unit\app** para escutar no pipe **unit\app** .</span><span class="sxs-lookup"><span data-stu-id="112c4-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="112c4-117">Digite **\\\\.\pipe\acct** para escutar no pipe **acct** .</span><span class="sxs-lookup"><span data-stu-id="112c4-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="112c4-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="112c4-118">See Also</span></span>  
 <span data-ttu-id="112c4-119">[Habilitar ou desabilitar um protocolo de rede de servidor](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="112c4-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="112c4-120">[Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="112c4-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="112c4-121">Criando uma cadeia de conexão válida usando pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="112c4-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
