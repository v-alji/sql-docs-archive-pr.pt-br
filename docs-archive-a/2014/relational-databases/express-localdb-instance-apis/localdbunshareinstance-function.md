---
title: Função LocalDBUnshareInstance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570030"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="ff564-102">Função LocalDBUnshareInstance</span><span class="sxs-lookup"><span data-stu-id="ff564-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="ff564-103">Interrompe o compartilhamento da instância especificada de LocalDB do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="ff564-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="ff564-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="ff564-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff564-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff564-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff564-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ff564-106">Parameters</span></span>  
 <span data-ttu-id="ff564-107">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="ff564-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="ff564-108">[Entrada] O nome compartilhado da instância de LocalDB a ser descompartilhada.</span><span class="sxs-lookup"><span data-stu-id="ff564-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="ff564-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="ff564-109">*dwFlags*</span></span>  
 <span data-ttu-id="ff564-110">[Entrada] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="ff564-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="ff564-111">Atualmente deve ser definido como 0.</span><span class="sxs-lookup"><span data-stu-id="ff564-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ff564-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="ff564-112">Returns</span></span>  
 <span data-ttu-id="ff564-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff564-113">S_OK</span></span>  
 <span data-ttu-id="ff564-114">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="ff564-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="ff564-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="ff564-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="ff564-116">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="ff564-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="ff564-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="ff564-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="ff564-118">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="ff564-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="ff564-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff564-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="ff564-120">O nome de instância especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="ff564-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="ff564-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="ff564-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="ff564-122">A instância especificada não existe.</span><span class="sxs-lookup"><span data-stu-id="ff564-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="ff564-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="ff564-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="ff564-124">É preciso ter privilégios de administrador para executar esta operação.</span><span class="sxs-lookup"><span data-stu-id="ff564-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="ff564-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="ff564-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="ff564-126">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="ff564-126">An unexpected error occurred.</span></span> <span data-ttu-id="ff564-127">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ff564-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff564-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="ff564-128">Remarks</span></span>  
 <span data-ttu-id="ff564-129">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ff564-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff564-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff564-130">See Also</span></span>  
 [<span data-ttu-id="ff564-131">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="ff564-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
