---
title: Mensagens de erro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684194"
---
# <a name="error-messages"></a><span data-ttu-id="6295a-102">Mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="6295a-102">Error Messages</span></span>
  <span data-ttu-id="6295a-103">O texto das mensagens retornadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client é colocado no parâmetro *MessageText* de **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="6295a-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="6295a-104">A origem de um erro é indicada pelo cabeçalho da mensagem:</span><span class="sxs-lookup"><span data-stu-id="6295a-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="6295a-105">[Microsoft][ODBC Driver Manager]</span><span class="sxs-lookup"><span data-stu-id="6295a-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="6295a-106">São erros gerados pelo Gerenciador de Driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="6295a-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="6295a-107">[Microsoft][ODBC Cursor Library]</span><span class="sxs-lookup"><span data-stu-id="6295a-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="6295a-108">São erros gerados pela biblioteca de cursores ODBC.</span><span class="sxs-lookup"><span data-stu-id="6295a-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="6295a-109">[Microsoft][SQL Server Native Client]</span><span class="sxs-lookup"><span data-stu-id="6295a-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="6295a-110">Esses erros são gerados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="6295a-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="6295a-111">Se não houver outros nós com o nome de uma Net-Library nem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é sinal de que o erro foi encontrado no driver.</span><span class="sxs-lookup"><span data-stu-id="6295a-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="6295a-112">O [SQL Server Native Client] [*Net-Transportname*]</span><span class="sxs-lookup"><span data-stu-id="6295a-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="6295a-113">Esses erros são gerados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] net-library, em que *net-Transportname* é o nome de exibição de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transporte de rede do cliente (por exemplo, pipes nomeados, memória compartilhada, soquetes TCP/IP ou via).</span><span class="sxs-lookup"><span data-stu-id="6295a-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="6295a-114">O restante da mensagem de erro contém a função Net-Library chamada e a função chamada na API de rede subjacente pela função TDS.</span><span class="sxs-lookup"><span data-stu-id="6295a-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="6295a-115">O código de erro *pfNative* retornado com esses erros é o código de erro da pilha de protocolo de rede subjacente.</span><span class="sxs-lookup"><span data-stu-id="6295a-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="6295a-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="6295a-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="6295a-117">São erros gerados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6295a-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6295a-118">O restante da mensagem de erro é o texto da mensagem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6295a-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6295a-119">O código *pfNative* retornado com esses erros é o número do erro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6295a-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6295a-120">Para obter mais informações sobre uma lista de mensagens de erro (e seus números) que podem ser retornados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte as colunas descrição e erro da tabela do sistema **sysmessages** no banco de dados **mestre** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6295a-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6295a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6295a-121">See Also</span></span>  
 [<span data-ttu-id="6295a-122">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="6295a-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
