---
title: Método SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SetVirtualDirectory method
ms.assetid: 1a25cb1d-38d5-401a-970b-87b642a780e4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7f45181f3f6a791f5cb64a7519285b6d2a87dd36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683986"
---
# <a name="setvirtualdirectory-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6e356-102">Método SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6e356-102">SetVirtualDirectory Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6e356-103">Define o nome do diretório virtual de um dado aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6e356-103">Sets the name of the virtual directory for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e356-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e356-104">Syntax</span></span>  
  
```vb  
Public Sub SetVirtualDirectory(ByVal Application As String, _  
    ByVal VirtualDirectory As String, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetVirtualDirectory(string Application, string VirtualDirectory,   
       int Lcid,out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e356-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="6e356-105">Parameters</span></span>  
 <span data-ttu-id="6e356-106">*Aplicativo*</span><span class="sxs-lookup"><span data-stu-id="6e356-106">*Application*</span></span>  
 <span data-ttu-id="6e356-107">O nome do aplicativo para o qual é necessário definir o diretório virtual.</span><span class="sxs-lookup"><span data-stu-id="6e356-107">The name of application for which to set the virtual directory.</span></span>  
  
 <span data-ttu-id="6e356-108">*VirtualDirectory*</span><span class="sxs-lookup"><span data-stu-id="6e356-108">*VirtualDirectory*</span></span>  
 <span data-ttu-id="6e356-109">O nome do diretório virtual.</span><span class="sxs-lookup"><span data-stu-id="6e356-109">The name of the virtual directory.</span></span>  
  
 <span data-ttu-id="6e356-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="6e356-110">*lcid*</span></span>  
 <span data-ttu-id="6e356-111">A identificação de localidade do diretório virtual.</span><span class="sxs-lookup"><span data-stu-id="6e356-111">The locale id for the virtual directory.</span></span>  
  
 <span data-ttu-id="6e356-112">*Erro*</span><span class="sxs-lookup"><span data-stu-id="6e356-112">*Error*</span></span>  
 <span data-ttu-id="6e356-113">[fora] A descrição do erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="6e356-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="6e356-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6e356-114">*HRESULT*</span></span>  
 <span data-ttu-id="6e356-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="6e356-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e356-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6e356-116">Return Value</span></span>  
 <span data-ttu-id="6e356-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="6e356-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6e356-118">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6e356-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e356-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e356-119">Remarks</span></span>  
 <span data-ttu-id="6e356-120">Um aplicativo pode ter somente um nome de diretório virtual para todas as reservas de URL.</span><span class="sxs-lookup"><span data-stu-id="6e356-120">An application can have only one virtual directory name for all URL reservations.</span></span>  
  
 <span data-ttu-id="6e356-121">VirtualDirectory deve seguir as convenções de nomenclatura para diretórios virtuais.</span><span class="sxs-lookup"><span data-stu-id="6e356-121">VirtualDirectory must conform to naming conventions for virtual directories.</span></span> <span data-ttu-id="6e356-122">VirtualDirectory não pode ser uma cadeia de caracteres vazia nem ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="6e356-122">VirtualDirectory must not be empty string or blank.</span></span>  
  
 <span data-ttu-id="6e356-123">Atualiza o valor do elemento \Configuration\URLReservations\Application\VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="6e356-123">Updates the value of the \Configuration\URLReservations\Application\VirtualDirectory element.</span></span> <span data-ttu-id="6e356-124">É bem-sucedido mesmo que nenhuma reserva de URL tenha sido criada.</span><span class="sxs-lookup"><span data-stu-id="6e356-124">Succeeds even if no URL reservations have been created yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e356-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e356-125">Requirements</span></span>  
 <span data-ttu-id="6e356-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e356-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e356-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e356-127">See Also</span></span>  
 [<span data-ttu-id="6e356-128">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6e356-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
