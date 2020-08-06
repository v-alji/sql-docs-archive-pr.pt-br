---
title: Função LocalDBGetVersions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685174"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="d8dc0-102">Função LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="d8dc0-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="d8dc0-103">Retorna todas as versões de LocalDB do SQL Server Express disponíveis no computador.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="d8dc0-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="d8dc0-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dc0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d8dc0-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8dc0-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d8dc0-106">Parameters</span></span>  
 <span data-ttu-id="d8dc0-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="d8dc0-107">*pVersionNames*</span></span>  
 <span data-ttu-id="d8dc0-108">Der Contém nomes das versões de LocalDB que estão disponíveis na estação de trabalho do usuário.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="d8dc0-109">*lpdwNumberOfVersions*</span><span class="sxs-lookup"><span data-stu-id="d8dc0-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="d8dc0-110">[Entrada/Saída] Na entrada, mantém o número de slots para versões no buffer *pVersionNames* .</span><span class="sxs-lookup"><span data-stu-id="d8dc0-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="d8dc0-111">Na saída, mantém o número de versões de LocalDB existentes.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d8dc0-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="d8dc0-112">Returns</span></span>  
 <span data-ttu-id="d8dc0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8dc0-113">S_OK</span></span>  
 <span data-ttu-id="d8dc0-114">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="d8dc0-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="d8dc0-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="d8dc0-116">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="d8dc0-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d8dc0-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="d8dc0-118">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="d8dc0-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d8dc0-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="d8dc0-120">O buffer de entrada é muito curto e o truncamento não foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="d8dc0-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="d8dc0-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="d8dc0-122">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-122">An unexpected error occurred.</span></span> <span data-ttu-id="d8dc0-123">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8dc0-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="d8dc0-124">Remarks</span></span>  
 <span data-ttu-id="d8dc0-125">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d8dc0-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dc0-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8dc0-126">See Also</span></span>  
 [<span data-ttu-id="d8dc0-127">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="d8dc0-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
