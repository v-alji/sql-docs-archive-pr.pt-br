---
title: Especificar configurações de informações de dispositivo em uma URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682085"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="ffdc7-102">Especificar configurações de informações do dispositivo em uma URL</span><span class="sxs-lookup"><span data-stu-id="ffdc7-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="ffdc7-103">As configurações de informações de dispositivo são parâmetros que são passados para uma extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="ffdc7-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="ffdc7-104">Se você usar os métodos do serviço Web do servidor de relatório do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para renderizar um relatório, um elemento XML `DeviceInfo` será passado como um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="ffdc7-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="ffdc7-105">Os elementos filhos do elemento `DeviceInfo` são específicos para as configurações de informações de dispositivo de extensões de renderização diferentes.</span><span class="sxs-lookup"><span data-stu-id="ffdc7-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="ffdc7-106">Você pode incluir as configurações de informações de dispositivo em uma URL usando a cadeia de caracteres do parâmetro *rc:tag=value* , em que *tag* é o nome do elemento de configurações de informações de dispositivo que estão sendo acessados.</span><span class="sxs-lookup"><span data-stu-id="ffdc7-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="ffdc7-107">Para obter mais informações sobre configurações de informações de dispositivo no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], confira [Passar configurações de informações de dispositivos para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="ffdc7-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffdc7-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ffdc7-108">Example</span></span>  
 <span data-ttu-id="ffdc7-109">O exemplo a seguir define o formato do relatório especificado para JPEG usando a configuração de informações do dispositivo *OutputFormat* da extensão de renderização de imagem (as quebras de linha foram adicionadas para legibilidade):</span><span class="sxs-lookup"><span data-stu-id="ffdc7-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffdc7-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffdc7-110">See Also</span></span>  
 <span data-ttu-id="ffdc7-111">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ffdc7-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="ffdc7-112">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="ffdc7-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
