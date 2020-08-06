---
title: Resultados da mensagem do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581784"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="38cca-102">Resultados da mensagem do SQL Server</span><span class="sxs-lookup"><span data-stu-id="38cca-102">SQL Server Message Results</span></span>
  <span data-ttu-id="38cca-103">As instruções a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] não geram [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de linhas do provedor de OLE DB do cliente nativo ou uma contagem de linha afetada quando executadas:</span><span class="sxs-lookup"><span data-stu-id="38cca-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="38cca-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="38cca-104">PRINT</span></span>  
  
-   <span data-ttu-id="38cca-105">RAISERROR com uma severidade de 10 ou menor</span><span class="sxs-lookup"><span data-stu-id="38cca-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="38cca-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="38cca-106">DBCC</span></span>  
  
-   <span data-ttu-id="38cca-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="38cca-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="38cca-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="38cca-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="38cca-109">Estas instruções retornam uma ou mais mensagens informativas ou fazem o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornar mensagens informativas em vez de resultados de contagens ou conjuntos de linhas.</span><span class="sxs-lookup"><span data-stu-id="38cca-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="38cca-110">Após a execução bem-sucedida, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna S_OK e as mensagens estão disponíveis para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB do cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="38cca-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="38cca-111">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna S_OK e tem uma ou mais mensagens informativas disponíveis após a execução de muitas [!INCLUDE[tsql](../../includes/tsql-md.md)] instruções ou a execução do consumidor de uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] função de membro do provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="38cca-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="38cca-112">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo que permite a especificação dinâmica do texto da consulta deve verificar as interfaces de erro depois de cada execução de função de membro, independentemente do valor do código de retorno, da presença ou da ausência de uma referência de interface **IRowset** ou **IMultipleResults** retornada ou de uma contagem de linhas afetadas.</span><span class="sxs-lookup"><span data-stu-id="38cca-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cca-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38cca-113">See Also</span></span>  
 [<span data-ttu-id="38cca-114">Erros</span><span class="sxs-lookup"><span data-stu-id="38cca-114">Errors</span></span>](errors.md)  
  
  
