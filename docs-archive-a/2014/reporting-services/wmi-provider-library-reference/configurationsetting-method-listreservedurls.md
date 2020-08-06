---
title: Método ListReservedURLs (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572911"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="55eef-102">Método ListReservedURLs (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="55eef-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="55eef-103">Lista as URLs reservadas para todos os aplicativos no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55eef-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55eef-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="55eef-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55eef-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="55eef-105">Parameters</span></span>  
 <span data-ttu-id="55eef-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="55eef-106">*Application[]*</span></span>  
 <span data-ttu-id="55eef-107">[fora] Os aplicativos que têm reservas de URL.</span><span class="sxs-lookup"><span data-stu-id="55eef-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="55eef-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="55eef-108">*UrlString[]*</span></span>  
 <span data-ttu-id="55eef-109">[fora] As URLs que estão reservadas.</span><span class="sxs-lookup"><span data-stu-id="55eef-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="55eef-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="55eef-110">*Account[]*</span></span>  
 <span data-ttu-id="55eef-111">[fora] Os nomes de conta associados com a conta para as reservas de URL.</span><span class="sxs-lookup"><span data-stu-id="55eef-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="55eef-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="55eef-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="55eef-113">[out] Os SIDs da conta associados com a conta para as reservas de URL.</span><span class="sxs-lookup"><span data-stu-id="55eef-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="55eef-114">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="55eef-114">*Length*</span></span>  
 <span data-ttu-id="55eef-115">[fora] O tamanho das matrizes retornadas pelo método.</span><span class="sxs-lookup"><span data-stu-id="55eef-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="55eef-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="55eef-116">*HRESULT*</span></span>  
 <span data-ttu-id="55eef-117">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="55eef-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55eef-118">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="55eef-118">Return Value</span></span>  
 <span data-ttu-id="55eef-119">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="55eef-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="55eef-120">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="55eef-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55eef-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="55eef-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55eef-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55eef-122">Requirements</span></span>  
 <span data-ttu-id="55eef-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55eef-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55eef-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55eef-124">See Also</span></span>  
 [<span data-ttu-id="55eef-125">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="55eef-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
