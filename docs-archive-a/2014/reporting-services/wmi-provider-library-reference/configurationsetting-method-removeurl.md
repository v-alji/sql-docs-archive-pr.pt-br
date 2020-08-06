---
title: Método RemoveURL (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a32989e8ce8986b785e829d8cc7fcf58fbbf240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575013"
---
# <a name="removeurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1c3c2-102">Método RemoveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="1c3c2-102">RemoveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1c3c2-103">Remove uma URL reservada para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-103">Removes a URL reserved for the report server.</span></span> <span data-ttu-id="1c3c2-104">Se houver várias URLs a serem removidas, isso deverá ser feito individualmente chamando-se esta API.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-104">If there are multiple URLs that need to be removed, this must be done one by one calling this API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3c2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c3c2-105">Syntax</span></span>  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c3c2-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1c3c2-106">Parameters</span></span>  
 <span data-ttu-id="1c3c2-107">*Aplicativo*</span><span class="sxs-lookup"><span data-stu-id="1c3c2-107">*Application*</span></span>  
 <span data-ttu-id="1c3c2-108">O nome do aplicativo do qual remover a reserva.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-108">The name of application for which to remove the reservation.</span></span>  
  
 <span data-ttu-id="1c3c2-109">*URLString*</span><span class="sxs-lookup"><span data-stu-id="1c3c2-109">*URLString*</span></span>  
 <span data-ttu-id="1c3c2-110">A URL para a reserva.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-110">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="1c3c2-111">*lcid*</span><span class="sxs-lookup"><span data-stu-id="1c3c2-111">*lcid*</span></span>  
 <span data-ttu-id="1c3c2-112">A localidade a ser usada para as mensagens de erro retornadas.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-112">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="1c3c2-113">*Erro*</span><span class="sxs-lookup"><span data-stu-id="1c3c2-113">*Error*</span></span>  
 <span data-ttu-id="1c3c2-114">[fora] A descrição do erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-114">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="1c3c2-115">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1c3c2-115">*HRESULT*</span></span>  
 <span data-ttu-id="1c3c2-116">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-116">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c3c2-117">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="1c3c2-117">Return Value</span></span>  
 <span data-ttu-id="1c3c2-118">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1c3c2-119">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-119">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c3c2-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c3c2-120">Remarks</span></span>  
 <span data-ttu-id="1c3c2-121">*UrlString* não inclui o nome do Diretório Virtual – o método [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) é fornecido para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-121">*UrlString* does not include the Virtual Directory name - the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="1c3c2-122">Antes de chamar o método [ReserveURL](configurationsetting-method-reserveurl.md) , forneça um valor para a propriedade de configuração VirtualDirectory do parâmetro *Application* .</span><span class="sxs-lookup"><span data-stu-id="1c3c2-122">Before calling the [ReserveURL](configurationsetting-method-reserveurl.md) method, you must supply a value for the VirtualDirectory configuration property for the *Application* parameter.</span></span> <span data-ttu-id="1c3c2-123">Use o método [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) para definir a propriedade VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-123">Use the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method to set the VirtualDirectory property.</span></span>  
  
 <span data-ttu-id="1c3c2-124">Se um Certificado SSL foi fornecido por [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e nenhuma outra URL precisar dele, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-124">If an SSL Certificate was provisioned by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and no other URLs need it, it is removed.</span></span>  
  
 <span data-ttu-id="1c3c2-125">Este método faz com que todos os domínios de aplicativo sem-configuração façam uma reciclagem e parem de funcionar durante esta operação; os domínios de aplicativo são reiniciados após o término da operação.</span><span class="sxs-lookup"><span data-stu-id="1c3c2-125">This method causes all non-configuration app domains to hard recycle and stop during this operation; app domains are restarted after this operation complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c3c2-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c3c2-126">Requirements</span></span>  
 <span data-ttu-id="1c3c2-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c3c2-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3c2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c3c2-128">See Also</span></span>  
 [<span data-ttu-id="1c3c2-129">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1c3c2-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
