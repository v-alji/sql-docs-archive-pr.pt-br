---
title: Método ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572913"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a4685-102">Método ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a4685-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a4685-103">Retorna a lista de instalações do servidor de relatório que estão presentes no banco de dados do servidor de relatório, independentemente de essas instalações terem acesso a informações seguras.</span><span class="sxs-lookup"><span data-stu-id="a4685-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4685-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4685-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4685-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="a4685-105">Parameters</span></span>  
 <span data-ttu-id="a4685-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="a4685-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="a4685-107">[fora] Uma matriz que contém os nomes de máquina das instalações do servidor de relatório no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a4685-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="a4685-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="a4685-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="a4685-109">[fora] Uma matriz que contém os nomes de instância de cada instalação do servidor de relatório no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a4685-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="a4685-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="a4685-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="a4685-111">[fora] Uma matriz que contém as IDs de instalação de cada instalação de servidor de relatório do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a4685-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="a4685-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="a4685-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="a4685-113">[fora] Uma matriz que contém o status de inicialização de cada instalação de servidor de relatório do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a4685-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="a4685-114">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="a4685-114">*Length*</span></span>  
 <span data-ttu-id="a4685-115">[fora] O tamanho das matrizes retornadas pelo método.</span><span class="sxs-lookup"><span data-stu-id="a4685-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="a4685-116">Todas as matrizes retornadas têm o mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="a4685-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="a4685-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a4685-117">*HRESULT*</span></span>  
 <span data-ttu-id="a4685-118">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="a4685-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="a4685-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="a4685-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="a4685-120">[fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.</span><span class="sxs-lookup"><span data-stu-id="a4685-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4685-121">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a4685-121">Return Value</span></span>  
 <span data-ttu-id="a4685-122">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="a4685-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a4685-123">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="a4685-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="a4685-124">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="a4685-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4685-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="a4685-125">Remarks</span></span>  
 <span data-ttu-id="a4685-126">O ListReportServersInDatabase lista as instalações do servidor de relatório que estão presentes no banco de dados do servidor de relatório, independentemente de terem acesso a informações seguras e retorna um conjunto de matrizes correspondentes contendo informações sobre cada instalação.</span><span class="sxs-lookup"><span data-stu-id="a4685-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4685-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4685-127">Requirements</span></span>  
 <span data-ttu-id="a4685-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4685-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4685-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4685-129">See Also</span></span>  
 [<span data-ttu-id="a4685-130">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a4685-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
