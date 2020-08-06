---
title: SQL Server, objeto Erros de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679314"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="57045-102">SQL Server, objeto SQL Errors</span><span class="sxs-lookup"><span data-stu-id="57045-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="57045-103">O objeto **SQLServer:SQL Errors** no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece contadores para monitorar **Erros SQL**.</span><span class="sxs-lookup"><span data-stu-id="57045-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="57045-104">Esta tabela descreve os contadores **Erros de SQL** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57045-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="57045-105">Contadores de Erros SQL do SQL Server</span><span class="sxs-lookup"><span data-stu-id="57045-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="57045-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="57045-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="57045-107">**Erros/s**</span><span class="sxs-lookup"><span data-stu-id="57045-107">**Errors/sec**</span></span>|<span data-ttu-id="57045-108">Número de erros/segundo.</span><span class="sxs-lookup"><span data-stu-id="57045-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="57045-109">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="57045-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="57045-110">Item</span><span class="sxs-lookup"><span data-stu-id="57045-110">Item</span></span>|<span data-ttu-id="57045-111">Definição</span><span class="sxs-lookup"><span data-stu-id="57045-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="57045-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="57045-112">**_Total**</span></span>|<span data-ttu-id="57045-113">Informações de todos os erros.</span><span class="sxs-lookup"><span data-stu-id="57045-113">Information for all errors.</span></span>|  
|<span data-ttu-id="57045-114">**Erros de BD Offline**</span><span class="sxs-lookup"><span data-stu-id="57045-114">**DB Offline Errors**</span></span>|<span data-ttu-id="57045-115">Rastreia erros severos que fazem com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] torne offline o banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="57045-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="57045-116">**Erros de Informação**</span><span class="sxs-lookup"><span data-stu-id="57045-116">**Info Errors**</span></span>|<span data-ttu-id="57045-117">Informações referentes a mensagens de erro que fornecem informações a usuários, mas não causam erros.</span><span class="sxs-lookup"><span data-stu-id="57045-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="57045-118">**Erros de Eliminação de Conexão**</span><span class="sxs-lookup"><span data-stu-id="57045-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="57045-119">Rastreia erros severos que fazem com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elimine a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="57045-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="57045-120">**Erros de Usuário**</span><span class="sxs-lookup"><span data-stu-id="57045-120">**User Errors**</span></span>|<span data-ttu-id="57045-121">Informações sobre erros de usuário.</span><span class="sxs-lookup"><span data-stu-id="57045-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57045-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57045-122">See Also</span></span>  
 [<span data-ttu-id="57045-123">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="57045-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
