---
title: Propriedade Detail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682115"
---
# <a name="detail-property"></a><span data-ttu-id="72987-102">Propriedade Detail</span><span class="sxs-lookup"><span data-stu-id="72987-102">Detail Property</span></span>
  <span data-ttu-id="72987-103">A propriedade **Detail** da classe [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** do  tem a seguinte estrutura XML:</span><span class="sxs-lookup"><span data-stu-id="72987-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="72987-104">Elementos</span><span class="sxs-lookup"><span data-stu-id="72987-104">Elements</span></span>  
 <span data-ttu-id="72987-105">**Detalhe**</span><span class="sxs-lookup"><span data-stu-id="72987-105">**Detail**</span></span>  
 <span data-ttu-id="72987-106">O elemento de alto nível que contém todos os outros elementos de detalhe de erro.</span><span class="sxs-lookup"><span data-stu-id="72987-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="72987-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="72987-107">**ErrorCode**</span></span>  
 <span data-ttu-id="72987-108">O código de erro específico do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72987-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="72987-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="72987-109">**HttpStatus**</span></span>  
 <span data-ttu-id="72987-110">O código de status HTTP.</span><span class="sxs-lookup"><span data-stu-id="72987-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="72987-111">**Message**</span><span class="sxs-lookup"><span data-stu-id="72987-111">**Message**</span></span>  
 <span data-ttu-id="72987-112">A mensagem de erro e o código de erro atribuídos pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72987-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="72987-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="72987-113">**HelpLink**</span></span>  
 <span data-ttu-id="72987-114">A URL do link de Ajuda para um site no qual poderão ser encontradas informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="72987-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="72987-115">Para obter mais informações, consulte [Elemento HelpLink](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="72987-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="72987-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="72987-116">**LinkID**</span></span>  
 <span data-ttu-id="72987-117">A ID atribuída ao link.</span><span class="sxs-lookup"><span data-stu-id="72987-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="72987-118">**NomeDoProduto**</span><span class="sxs-lookup"><span data-stu-id="72987-118">**ProductName**</span></span>  
 <span data-ttu-id="72987-119">O nome do produto.</span><span class="sxs-lookup"><span data-stu-id="72987-119">The name of the product.</span></span> <span data-ttu-id="72987-120">O valor padrão é **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="72987-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="72987-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="72987-121">**ProductVersion**</span></span>  
 <span data-ttu-id="72987-122">A versão do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72987-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="72987-123">O tamanho máximo é de 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="72987-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="72987-124">O formato do número da versão deve ser assim: 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="72987-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="72987-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="72987-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="72987-126">A ID de localidade ou ID de idioma da DLL INTL do aplicativo (por exemplo, 0x41A).</span><span class="sxs-lookup"><span data-stu-id="72987-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="72987-127">**Operacional**</span><span class="sxs-lookup"><span data-stu-id="72987-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="72987-128">O sistema operacional em que o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="72987-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="72987-129">Os valores válidos incluem **0** para o sistema operacional independente, **1** para o [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)] e **16** para o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="72987-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="72987-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="72987-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="72987-131">A ID de localidade ou a ID de idioma do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="72987-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="72987-132">Por exemplo, o valor para a versão francesa de Windows é 0x040c.</span><span class="sxs-lookup"><span data-stu-id="72987-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="72987-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="72987-133">**MoreInformation**</span></span>  
 <span data-ttu-id="72987-134">Uma cadeia de caracteres XML que contém exceções aninhadas ocorridas durante a execução do método.</span><span class="sxs-lookup"><span data-stu-id="72987-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="72987-135">**Origem**</span><span class="sxs-lookup"><span data-stu-id="72987-135">**Source**</span></span>  
 <span data-ttu-id="72987-136">Um elemento filho de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="72987-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="72987-137">A origem do erro.</span><span class="sxs-lookup"><span data-stu-id="72987-137">The source of the error.</span></span>  
  
 <span data-ttu-id="72987-138">**Message**</span><span class="sxs-lookup"><span data-stu-id="72987-138">**Message**</span></span>  
 <span data-ttu-id="72987-139">Um elemento filho de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="72987-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="72987-140">A mensagem de erro de uma exceção aninhada.</span><span class="sxs-lookup"><span data-stu-id="72987-140">The error message of a nested exception.</span></span> <span data-ttu-id="72987-141">Esse elemento inclui atributos XML para **ErrorCode** e **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="72987-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="72987-142">**Warnings**</span><span class="sxs-lookup"><span data-stu-id="72987-142">**Warnings**</span></span>  
 <span data-ttu-id="72987-143">Uma cadeia de caracteres XML que contém os avisos retornados do processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="72987-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72987-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72987-144">See Also</span></span>  
 <span data-ttu-id="72987-145">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="72987-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="72987-146">[Classe SoapException Reporting Services](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="72987-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="72987-147">Usando a propriedade Detail para manipular erros específicos</span><span class="sxs-lookup"><span data-stu-id="72987-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
