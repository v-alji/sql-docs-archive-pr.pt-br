---
title: Função LocalDBStartTracing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686279"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="8c68d-102">Função LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="8c68d-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="8c68d-103">Habilita o rastreamento de chamadas de API para todas as instâncias de LocalDB do SQL Server Express de propriedade do usuário atual do Windows.</span><span class="sxs-lookup"><span data-stu-id="8c68d-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="8c68d-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="8c68d-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c68d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c68d-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="8c68d-106">Retornos</span><span class="sxs-lookup"><span data-stu-id="8c68d-106">Returns</span></span>  
 <span data-ttu-id="8c68d-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c68d-107">S_OK</span></span>  
 <span data-ttu-id="8c68d-108">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="8c68d-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="8c68d-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="8c68d-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="8c68d-110">Falha ao iniciar o mecanismo XEvent na API da Instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8c68d-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="8c68d-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8c68d-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="8c68d-112">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="8c68d-112">An unexpected error occurred.</span></span> <span data-ttu-id="8c68d-113">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8c68d-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c68d-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="8c68d-114">Remarks</span></span>  
 <span data-ttu-id="8c68d-115">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8c68d-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c68d-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c68d-116">See Also</span></span>  
 [<span data-ttu-id="8c68d-117">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="8c68d-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
