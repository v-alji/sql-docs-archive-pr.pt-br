---
title: Método GetDatabaseVersionDisplayName (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572917"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="6430c-102">Método GetDatabaseVersionDisplayName (WMI)</span><span class="sxs-lookup"><span data-stu-id="6430c-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="6430c-103">Obtém o nome para exibição para uma determinada cadeia de caracteres da versão do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="6430c-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6430c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6430c-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6430c-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="6430c-105">Parameters</span></span>  
 <span data-ttu-id="6430c-106">*Versão*</span><span class="sxs-lookup"><span data-stu-id="6430c-106">*Version*</span></span>  
 <span data-ttu-id="6430c-107">Uma cadeia de caracteres que contém a cadeia de caracteres de versão para um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="6430c-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="6430c-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="6430c-108">*DisplayName*</span></span>  
 <span data-ttu-id="6430c-109">[fora] Uma cadeia de caracteres que contém o nome para exibição que corresponde à versão fornecida.</span><span class="sxs-lookup"><span data-stu-id="6430c-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="6430c-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6430c-110">*HRESULT*</span></span>  
 <span data-ttu-id="6430c-111">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="6430c-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6430c-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="6430c-112">Remarks</span></span>  
 <span data-ttu-id="6430c-113">A tabela a seguir mostra o mapeamento da versão do banco de dados para exibir a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6430c-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="6430c-114">**Versão**</span><span class="sxs-lookup"><span data-stu-id="6430c-114">**Release**</span></span>|`Version`|<span data-ttu-id="6430c-115">**Nome de exibição**</span><span class="sxs-lookup"><span data-stu-id="6430c-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="6430c-116">RS 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="6430c-116">RS 2005 SP2</span></span>|<span data-ttu-id="6430c-117">@DBVersion = 'C.0.8.54'</span><span class="sxs-lookup"><span data-stu-id="6430c-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="6430c-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="6430c-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="6430c-119">RS 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6430c-119">RS 2005 SP1</span></span>|<span data-ttu-id="6430c-120">@DBVersion = 'C.0.8.43'</span><span class="sxs-lookup"><span data-stu-id="6430c-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="6430c-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6430c-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="6430c-122">RS 2005 RTM</span><span class="sxs-lookup"><span data-stu-id="6430c-122">RS 2005 RTM</span></span>|<span data-ttu-id="6430c-123">@DBVersion = 'C.0.8.40'</span><span class="sxs-lookup"><span data-stu-id="6430c-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="6430c-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="6430c-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="6430c-125">RS 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="6430c-125">RS 2000 SP2</span></span>|<span data-ttu-id="6430c-126">@DBVersion = 'C.0.6.54'</span><span class="sxs-lookup"><span data-stu-id="6430c-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="6430c-127">SQL Server 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="6430c-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="6430c-128">RS 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="6430c-128">RS 2000 SP1</span></span>|<span data-ttu-id="6430c-129">@DBVersion = 'C.0.6.51'</span><span class="sxs-lookup"><span data-stu-id="6430c-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="6430c-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="6430c-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="6430c-131">RS 2000 RTM</span><span class="sxs-lookup"><span data-stu-id="6430c-131">RS 2000 RTM</span></span>|<span data-ttu-id="6430c-132">@DBVersion = 'C.0.6.43'</span><span class="sxs-lookup"><span data-stu-id="6430c-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="6430c-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="6430c-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="6430c-134">Hotfix</span><span class="sxs-lookup"><span data-stu-id="6430c-134">Hotfix</span></span>||<span data-ttu-id="6430c-135">Versão mais próxima aplicável</span><span class="sxs-lookup"><span data-stu-id="6430c-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="6430c-136">Para uma *Versão* anterior ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000, é retornado um HRESULT de ACT_E_BAD_VERSION.</span><span class="sxs-lookup"><span data-stu-id="6430c-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6430c-137">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6430c-137">Return Value</span></span>  
 <span data-ttu-id="6430c-138">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="6430c-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6430c-139">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="6430c-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6430c-140">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="6430c-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6430c-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6430c-141">Requirements</span></span>  
 <span data-ttu-id="6430c-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6430c-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6430c-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6430c-143">See Also</span></span>  
 [<span data-ttu-id="6430c-144">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6430c-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
