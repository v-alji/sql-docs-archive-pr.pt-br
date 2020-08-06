---
title: Função LocalDBStopTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570029"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="809d7-102">Função LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="809d7-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="809d7-103">Desabilita o rastreamento de chamadas de API para todas as instâncias LocalDB do SQL Server Express de propriedade do usuário atual do Windows.</span><span class="sxs-lookup"><span data-stu-id="809d7-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="809d7-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="809d7-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809d7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="809d7-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="809d7-106">Retornos</span><span class="sxs-lookup"><span data-stu-id="809d7-106">Returns</span></span>  
 <span data-ttu-id="809d7-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="809d7-107">S_OK</span></span>  
 <span data-ttu-id="809d7-108">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="809d7-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="809d7-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="809d7-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="809d7-110">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="809d7-110">An unexpected error occurred.</span></span> <span data-ttu-id="809d7-111">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="809d7-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="809d7-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="809d7-112">Remarks</span></span>  
 <span data-ttu-id="809d7-113">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="809d7-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809d7-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="809d7-114">See Also</span></span>  
 [<span data-ttu-id="809d7-115">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="809d7-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
