---
title: Método GetReportServerUrls (WMI MSReportServer_Instance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681377"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="c922e-102">Método GetReportServerUrls (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="c922e-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="c922e-103">Retorna uma lista de URLs que os usuários podem usar para acessar o servidor de relatório e o gerenciador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c922e-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c922e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c922e-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c922e-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="c922e-105">Parameters</span></span>  
 <span data-ttu-id="c922e-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="c922e-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="c922e-107">Uma matriz que contém os aplicativos que estão instalados.</span><span class="sxs-lookup"><span data-stu-id="c922e-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="c922e-108">Os valores são `ReportServerWebService` ou `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="c922e-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="c922e-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="c922e-109">*URLs[]*</span></span>  
 <span data-ttu-id="c922e-110">Uma matriz que contém as Urls registradas com êxito.</span><span class="sxs-lookup"><span data-stu-id="c922e-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="c922e-111">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="c922e-111">*Length*</span></span>  
 <span data-ttu-id="c922e-112">Um valor de inteiro que contém o tamanho das matrizes retornadas.</span><span class="sxs-lookup"><span data-stu-id="c922e-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="c922e-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c922e-113">*HRESULT*</span></span>  
 <span data-ttu-id="c922e-114">Um valor que indica êxito ou um código de erro.</span><span class="sxs-lookup"><span data-stu-id="c922e-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="c922e-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c922e-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c922e-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="c922e-116">Remarks</span></span>  
 <span data-ttu-id="c922e-117">Os métodos expostos pelos objetos de gerenciamento de WMI são chamados pela função InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="c922e-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="c922e-118">Para obter mais informações, consulte "Executando Métodos em Objetos de Gerenciamento" na documentação da WMI do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c922e-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c922e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c922e-119">Requirements</span></span>  
 <span data-ttu-id="c922e-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c922e-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c922e-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c922e-121">See Also</span></span>  
 [<span data-ttu-id="c922e-122">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c922e-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
