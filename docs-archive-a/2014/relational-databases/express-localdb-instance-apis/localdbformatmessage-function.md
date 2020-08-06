---
title: Função LocalDBFormatMessage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBFormatMessage
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 31b3152a-94cf-4f75-a31b-296d7dd16dbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ece28f19e3488fae248bf26c3a54a018ba6efd0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686277"
---
# <a name="localdbformatmessage-function"></a><span data-ttu-id="e0310-102">Função LocalDBFormatMessage</span><span class="sxs-lookup"><span data-stu-id="e0310-102">LocalDBFormatMessage Function</span></span>
  <span data-ttu-id="e0310-103">Retorna a descrição textual localizada para o erro de LocalDB do SQL Server Express especificado.</span><span class="sxs-lookup"><span data-stu-id="e0310-103">Returns the localized textual description for the specified SQL Server Express LocalDB error.</span></span>  
  
 <span data-ttu-id="e0310-104">**Arquivo de cabeçalho:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="e0310-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0310-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e0310-105">Syntax</span></span>  
  
```  
HRESULT LocalDBFormatMessage(  
           HRESULT hrLocalDB,  
           DWORD dwFlags,   
           DWORD dwLanguageId,   
           LPWSTR wszMessage,   
           LPDWORD lpcchMessage   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0310-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e0310-106">Parameters</span></span>  
 <span data-ttu-id="e0310-107">*hrLocalDB*</span><span class="sxs-lookup"><span data-stu-id="e0310-107">*hrLocalDB*</span></span>  
 <span data-ttu-id="e0310-108">[Entrada] O código de erro de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0310-108">[Input] The LocalDB error code.</span></span>  
  
 <span data-ttu-id="e0310-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="e0310-109">*dwFlags*</span></span>  
 <span data-ttu-id="e0310-110">[Entrada] Os sinalizadores que especificam o comportamento desta função.</span><span class="sxs-lookup"><span data-stu-id="e0310-110">[Input] The flags specifying the behavior of this function.</span></span>  
  
 <span data-ttu-id="e0310-111">Sinalizadores disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e0310-111">Available flags:</span></span>  
  
 <span data-ttu-id="e0310-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="e0310-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span></span>  
 <span data-ttu-id="e0310-113">Se o buffer de entrada for muito curto, a mensagem de erro será truncada para ajustar o buffer.</span><span class="sxs-lookup"><span data-stu-id="e0310-113">If the input buffer is too short, the error message will be truncated to fit the buffer.</span></span>  
  
 <span data-ttu-id="e0310-114">*dwLanguageId*</span><span class="sxs-lookup"><span data-stu-id="e0310-114">*dwLanguageId*</span></span>  
 <span data-ttu-id="e0310-115">[Entrada] O idioma desejado (LANGID) ou 0, nesse caso, a ordem do idioma de Win32 FormatMessage é usada.</span><span class="sxs-lookup"><span data-stu-id="e0310-115">[Input] The language desired (LANGID) or 0, in which case the Win32 FormatMessage language order is used.</span></span>  
  
 <span data-ttu-id="e0310-116">*wszMessage*</span><span class="sxs-lookup"><span data-stu-id="e0310-116">*wszMessage*</span></span>  
 <span data-ttu-id="e0310-117">[Saída] O buffer para armazenar a mensagem de erro de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0310-117">[Output] The buffer to store the LocalDB error message.</span></span>  
  
 <span data-ttu-id="e0310-118">*lpcchMessage*</span><span class="sxs-lookup"><span data-stu-id="e0310-118">*lpcchMessage*</span></span>  
 <span data-ttu-id="e0310-119">[Entrada/Saída] Na entrada contém o tamanho do buffer *wszMessage* em caracteres.</span><span class="sxs-lookup"><span data-stu-id="e0310-119">[Input/Output] On input contains the size of the *wszMessage* buffer in characters.</span></span> <span data-ttu-id="e0310-120">Na saída, se o tamanho de buffer especificado for muito pequeno, conterá o tamanho de buffer necessário em caracteres, incluindo quaisquer caracteres nulos à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e0310-120">On output, if the given buffer size is too small, contains the buffer size required in characters, including any trailing nulls.</span></span> <span data-ttu-id="e0310-121">Se a função tiver sucesso, ela conterá o número de caracteres na mensagem, excluindo os caracteres nulos à direita.</span><span class="sxs-lookup"><span data-stu-id="e0310-121">If the function succeeds, contains the number of characters in the message, excluding any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e0310-122">Retornos</span><span class="sxs-lookup"><span data-stu-id="e0310-122">Returns</span></span>  
 <span data-ttu-id="e0310-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0310-123">S_OK</span></span>  
 <span data-ttu-id="e0310-124">A função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e0310-124">The function succeeded.</span></span>  
  
 [<span data-ttu-id="e0310-125">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="e0310-125">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="e0310-126">O LocalDB do SQL Server Express não está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="e0310-126">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="e0310-127">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="e0310-127">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="e0310-128">Um ou mais parâmetros de entrada especificados são inválidos.</span><span class="sxs-lookup"><span data-stu-id="e0310-128">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="e0310-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span><span class="sxs-lookup"><span data-stu-id="e0310-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span></span>](../express-localdb-error-messages/localdb-error-unknown-error-code.md)  
 <span data-ttu-id="e0310-130">A mensagem solicitada não existe.</span><span class="sxs-lookup"><span data-stu-id="e0310-130">The requested message does not exist.</span></span>  
  
 [<span data-ttu-id="e0310-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="e0310-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>](../express-localdb-error-messages/localdb-error-unknown-language-id.md)  
 <span data-ttu-id="e0310-132">A mensagem não está disponível no idioma solicitado.</span><span class="sxs-lookup"><span data-stu-id="e0310-132">The message is not available in the requested language.</span></span>  
  
 [<span data-ttu-id="e0310-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e0310-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="e0310-134">O buffer de entrada *wszMessage* é muito curto e o truncamento não foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="e0310-134">The input buffer *wszMessage* is too short, and truncation is not requested.</span></span>  
  
 [<span data-ttu-id="e0310-135">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="e0310-135">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="e0310-136">Erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="e0310-136">An unexpected error occurred.</span></span> <span data-ttu-id="e0310-137">Consulte o log de eventos para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="e0310-137">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0310-138">Comentários</span><span class="sxs-lookup"><span data-stu-id="e0310-138">Remarks</span></span>  
 <span data-ttu-id="e0310-139">Para obter uma amostra do código que usa a API LocalDB, consulte [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e0310-139">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0310-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0310-140">See Also</span></span>  
 [<span data-ttu-id="e0310-141">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="e0310-141">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
