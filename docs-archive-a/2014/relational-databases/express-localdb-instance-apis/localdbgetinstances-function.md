---
title: Função LocalDBGetInstances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678744"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="68619-102">Função LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="68619-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="68619-103">Retorna todas as instâncias de LocalDB do SQL Server Express com a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="68619-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="68619-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="68619-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68619-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68619-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68619-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68619-106">Parameters</span></span>  
 <span data-ttu-id="68619-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="68619-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="68619-108">Der Quando essa função retorna, contém os nomes das instâncias de LocalDB nomeadas e padrão na estação de trabalho do usuário.</span><span class="sxs-lookup"><span data-stu-id="68619-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="68619-109">*lpdwNumberOfInstances*</span><span class="sxs-lookup"><span data-stu-id="68619-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="68619-110">[Entrada/Saída] Na entrada, contém o número de slots dos nomes de instância no buffer *pInstanceNames* .</span><span class="sxs-lookup"><span data-stu-id="68619-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="68619-111">Na saída, contém o número de instâncias LocalDB encontradas na estação de trabalho do usuário.</span><span class="sxs-lookup"><span data-stu-id="68619-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="68619-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="68619-112">Returns</span></span>  
 <span data-ttu-id="68619-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="68619-113">S_OK</span></span>  
 <span data-ttu-id="68619-114">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="68619-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="68619-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="68619-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="68619-116">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="68619-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="68619-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="68619-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="68619-118">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="68619-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="68619-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="68619-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="68619-120">O buffer de entrada é muito curto e o truncamento não foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="68619-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="68619-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="68619-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="68619-122">O caminho em que a instância deve estar armazenada não é maior que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="68619-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="68619-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="68619-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="68619-124">Não é possível acessar um registro de instância.</span><span class="sxs-lookup"><span data-stu-id="68619-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="68619-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="68619-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="68619-126">Uma configuração de instância está corrompida.</span><span class="sxs-lookup"><span data-stu-id="68619-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="68619-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="68619-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="68619-128">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="68619-128">An unexpected error occurred.</span></span> <span data-ttu-id="68619-129">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="68619-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68619-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="68619-130">Remarks</span></span>  
 <span data-ttu-id="68619-131">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="68619-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68619-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68619-132">See Also</span></span>  
 [<span data-ttu-id="68619-133">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="68619-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
