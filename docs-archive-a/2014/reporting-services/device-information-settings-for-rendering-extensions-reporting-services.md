---
title: Configurações de informações de dispositivos para extensões de renderização (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682157"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="800e2-102">Configurações de informações de dispositivos para extensões de renderização (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="800e2-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="800e2-103">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], as configurações de informações de dispositivo são usadas para passar parâmetros de renderização para uma extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="800e2-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="800e2-104">Cada extensão de renderização aceita um conjunto específico de configurações.</span><span class="sxs-lookup"><span data-stu-id="800e2-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="800e2-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="800e2-105">In This Section</span></span>  
  
|<span data-ttu-id="800e2-106">Tópico</span><span class="sxs-lookup"><span data-stu-id="800e2-106">Topic</span></span>|<span data-ttu-id="800e2-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="800e2-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="800e2-108">Configurações de informações do dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="800e2-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="800e2-109">Descreve as configurações de informações de dispositivo associadas à saída de renderização compatível com o Atom.</span><span class="sxs-lookup"><span data-stu-id="800e2-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="800e2-110">Configurações das informações do dispositivo CSV</span><span class="sxs-lookup"><span data-stu-id="800e2-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="800e2-111">Descreve as configurações de informações de dispositivo associadas à saída de renderização de CSV.</span><span class="sxs-lookup"><span data-stu-id="800e2-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="800e2-112">Configurações das informações do dispositivo do Excel</span><span class="sxs-lookup"><span data-stu-id="800e2-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="800e2-113">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do Excel.</span><span class="sxs-lookup"><span data-stu-id="800e2-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="800e2-114">Configurações de informações de dispositivo do Word</span><span class="sxs-lookup"><span data-stu-id="800e2-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="800e2-115">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do Word.</span><span class="sxs-lookup"><span data-stu-id="800e2-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="800e2-116">Configurações de informações do dispositivo HTML</span><span class="sxs-lookup"><span data-stu-id="800e2-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="800e2-117">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do HTML.</span><span class="sxs-lookup"><span data-stu-id="800e2-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="800e2-118">Configurações de informações de dispositivo de imagem</span><span class="sxs-lookup"><span data-stu-id="800e2-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="800e2-119">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do IMAGE.</span><span class="sxs-lookup"><span data-stu-id="800e2-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="800e2-120">Configurações das informações do dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="800e2-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="800e2-121">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do MHTML.</span><span class="sxs-lookup"><span data-stu-id="800e2-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="800e2-122">Configurações de informações do dispositivo PDF</span><span class="sxs-lookup"><span data-stu-id="800e2-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="800e2-123">Descreve as configurações de informações de dispositivo que são associadas à saída de renderização do PDF.</span><span class="sxs-lookup"><span data-stu-id="800e2-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="800e2-124">Configurações de informações do dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="800e2-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="800e2-125">Descreve as configurações de informações de dispositivos que estão associadas à saída de renderização do XML.</span><span class="sxs-lookup"><span data-stu-id="800e2-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="800e2-126">Configurações de informações do dispositivo RGDI</span><span class="sxs-lookup"><span data-stu-id="800e2-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="800e2-127">Descreve as configurações de informações de dispositivos que estão associadas à saída de renderização do RGDI.</span><span class="sxs-lookup"><span data-stu-id="800e2-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="800e2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="800e2-128">See Also</span></span>  
 [<span data-ttu-id="800e2-129">Personalizar parâmetros de extensão de renderização em RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="800e2-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
