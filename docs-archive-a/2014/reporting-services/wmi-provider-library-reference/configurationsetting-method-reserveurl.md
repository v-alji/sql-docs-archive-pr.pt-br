---
title: Método ReserveURL (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684003"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="94720-102">Método ReserveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="94720-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="94720-103">Adiciona uma reserva de URL para um determinado aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94720-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94720-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="94720-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94720-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="94720-105">Parameters</span></span>  
 <span data-ttu-id="94720-106">*Aplicativo*</span><span class="sxs-lookup"><span data-stu-id="94720-106">*Application*</span></span>  
 <span data-ttu-id="94720-107">O nome do aplicativo para o qual reservar a URL.</span><span class="sxs-lookup"><span data-stu-id="94720-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="94720-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="94720-108">*URLString*</span></span>  
 <span data-ttu-id="94720-109">A URL para a reserva.</span><span class="sxs-lookup"><span data-stu-id="94720-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="94720-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="94720-110">*lcid*</span></span>  
 <span data-ttu-id="94720-111">A localidade a ser usada para as mensagens de erro retornadas.</span><span class="sxs-lookup"><span data-stu-id="94720-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="94720-112">*Erro*</span><span class="sxs-lookup"><span data-stu-id="94720-112">*Error*</span></span>  
 <span data-ttu-id="94720-113">[fora] A descrição do erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="94720-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="94720-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="94720-114">*HRESULT*</span></span>  
 <span data-ttu-id="94720-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="94720-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94720-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="94720-116">Return Value</span></span>  
 <span data-ttu-id="94720-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="94720-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="94720-118">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="94720-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94720-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="94720-119">Remarks</span></span>  
 <span data-ttu-id="94720-120">*UrlString* não inclui o nome do diretório virtual.</span><span class="sxs-lookup"><span data-stu-id="94720-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="94720-121">O método [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) é disponibilizado para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="94720-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="94720-122">As reservas de URL são criadas para a conta atual de serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="94720-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="94720-123">Para alterar a conta de serviço do Windows, é necessário atualizar todas as reservas de URL manualmente.</span><span class="sxs-lookup"><span data-stu-id="94720-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="94720-124">Este método faz com que todos os domínios de aplicativo façam uma reciclagem agressiva.</span><span class="sxs-lookup"><span data-stu-id="94720-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="94720-125">Os domínios de aplicativo são reiniciados após o término desta operação.</span><span class="sxs-lookup"><span data-stu-id="94720-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94720-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94720-126">Requirements</span></span>  
 <span data-ttu-id="94720-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94720-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94720-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94720-128">See Also</span></span>  
 [<span data-ttu-id="94720-129">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="94720-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
