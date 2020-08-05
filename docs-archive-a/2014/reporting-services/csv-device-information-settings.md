---
title: Configurações de informações de dispositivo CSV | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CSV [Reporting Services]
- device information settings [Reporting Services], CSV rendering
ms.assetid: f96f83a6-50bc-48ce-9fcd-fd9e1952d40a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00369f2da9b248bcf66d551b5066f4ccd54e42e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573799"
---
# <a name="csv-device-information-settings"></a><span data-ttu-id="a9c97-102">Configurações das informações do dispositivo CSV</span><span class="sxs-lookup"><span data-stu-id="a9c97-102">CSV Device Information Settings</span></span>
  <span data-ttu-id="a9c97-103">As configurações de informações de dispositivo para a extensão de renderização de CSV permitem que os delimitadores e os qualificadores sejam alterados e o tratamento de quebra de linha seja especificado.</span><span class="sxs-lookup"><span data-stu-id="a9c97-103">The device information settings for the CSV rendering extension allow delimiters and qualifiers to be changed and line break handling to be specified.</span></span> <span data-ttu-id="a9c97-104">A extensão do arquivo também pode ser enviada, como também a codificação e inclusão de linhas de cabeçalho na saída.</span><span class="sxs-lookup"><span data-stu-id="a9c97-104">The extension of the file can also be submitted, as well as the encoding and inclusion of header rows in the output.</span></span> <span data-ttu-id="a9c97-105">Como é provável que os delimitadores sejam caracteres especiais, você deverá codificá-los em uma seção CDATA, se as configurações forem gravadas como XML.</span><span class="sxs-lookup"><span data-stu-id="a9c97-105">Because delimiters are likely to be special characters, you should encode them in a CDATA section, if the settings are written as XML.</span></span>  
  
 <span data-ttu-id="a9c97-106">A tabela a seguir lista as configurações de informações de dispositivo para renderização no formato Texto.</span><span class="sxs-lookup"><span data-stu-id="a9c97-106">The following table lists the device information settings for rendering in Text format.</span></span>  
  
|<span data-ttu-id="a9c97-107">Configuração</span><span class="sxs-lookup"><span data-stu-id="a9c97-107">Setting</span></span>|<span data-ttu-id="a9c97-108">Valor</span><span class="sxs-lookup"><span data-stu-id="a9c97-108">Value</span></span>|  
|-------------|-----------|  
|`Encoding`|<span data-ttu-id="a9c97-109">O nome da IANA (Internet Assigned Numbers Authority) de uma codificação de caracteres com suporte do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9c97-109">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="a9c97-110">O valor padrão é `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-110">The default value is `UTF-8`.</span></span> <span data-ttu-id="a9c97-111">Exemplos de outros valores incluem ASCII, UTF-7 e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="a9c97-111">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
|`ExcelMode`|<span data-ttu-id="a9c97-112">Especifica se a saída de destino é para o Excel.</span><span class="sxs-lookup"><span data-stu-id="a9c97-112">Specifies that the target output is for Excel.</span></span> <span data-ttu-id="a9c97-113">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-113">The default value is `true`.</span></span>|  
|`FieldDelimiter`|<span data-ttu-id="a9c97-114">A cadeia de caracteres delimitadora para colocar no resultado.</span><span class="sxs-lookup"><span data-stu-id="a9c97-114">The delimiter string to put in the result.</span></span> <span data-ttu-id="a9c97-115">O valor padrão é uma vírgula (,).</span><span class="sxs-lookup"><span data-stu-id="a9c97-115">The default value is a comma (,).</span></span> <span data-ttu-id="a9c97-116">Você deve codificar o valor dessas informações de dispositivo ao transmiti-lo em uma URL.</span><span class="sxs-lookup"><span data-stu-id="a9c97-116">You should URL encode the value of this device information when passing it on a URL.</span></span> <span data-ttu-id="a9c97-117">Por exemplo, um caractere de tabulação como um delimitador deve ser "%09".</span><span class="sxs-lookup"><span data-stu-id="a9c97-117">For example, a tab character as a delimiter should be "%09".</span></span><br /><br /> <span data-ttu-id="a9c97-118">Você pode alterar o delimitador de campo padrão para qualquer caractere que desejar, inclusive o TAB, alterando as configurações de informações de dispositivo no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="a9c97-118">You can change the default field delimiter to any character that you want, including TAB, by changing the device information settings in the configuration file.</span></span> <span data-ttu-id="a9c97-119">Por exemplo, para usar TAB, atualize a configuração FieldDelimiter para \<FieldDelimiter xml:space="preserve"> [TAB]\</FieldDelimiter></span><span class="sxs-lookup"><span data-stu-id="a9c97-119">For example, to use TAB, update the FieldDelimiter setting to \<FieldDelimiter xml:space="preserve">[TAB]\</FieldDelimiter></span></span><br /><br /> <span data-ttu-id="a9c97-120">No exemplo [TAB] é um caractere de tabulação real, o que significa que aparece espaço em branco no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="a9c97-120">In the example [TAB] is an actual tab character, which means that whitespace appears in the configuration file.</span></span> <span data-ttu-id="a9c97-121">O atributo "xml:space" instrui os analisadores para preservarem o espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="a9c97-121">The "xml:space" attribute tells parsers to preserve whitespace.</span></span>|  
|`FileExtension`|<span data-ttu-id="a9c97-122">A extensão do arquivo a ser colocada no resultado.</span><span class="sxs-lookup"><span data-stu-id="a9c97-122">The file extension to put on the result.</span></span> <span data-ttu-id="a9c97-123">O valor padrão é `.CSV`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-123">The default value is `.CSV`.</span></span> <span data-ttu-id="a9c97-124">Se `FileExtension` e `Extension` forem especificados, então, o `FileExtension` terá precedência.</span><span class="sxs-lookup"><span data-stu-id="a9c97-124">If both `FileExtension` and `Extension` are specified then `FileExtension` will take precedence.</span></span>|  
|<span data-ttu-id="a9c97-125">**NoHeader**</span><span class="sxs-lookup"><span data-stu-id="a9c97-125">**NoHeader**</span></span>|<span data-ttu-id="a9c97-126">Indica se a linha do cabeçalho será excluída da saída.</span><span class="sxs-lookup"><span data-stu-id="a9c97-126">Indicates whether the header row is excluded from the output.</span></span> <span data-ttu-id="a9c97-127">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-127">The default value is `false`.</span></span>|  
|`Qualifier`|<span data-ttu-id="a9c97-128">A cadeia de caracteres do qualificador para colocar ao redor de resultados que contêm o delimitador de campo ou delimitador de registro.</span><span class="sxs-lookup"><span data-stu-id="a9c97-128">The qualifier string to put around results that contain the field delimiter or record delimiter.</span></span> <span data-ttu-id="a9c97-129">Se os resultados contiverem o qualificador, ele será repetido.</span><span class="sxs-lookup"><span data-stu-id="a9c97-129">If the results contain the qualifier, the qualifier is repeated.</span></span> <span data-ttu-id="a9c97-130">A configuração `Qualifier` deve ser diferente das configurações`FieldDelimiter` e `RecordDelimiter`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-130">The `Qualifier` setting must be different from the `FieldDelimiter` and `RecordDelimiter` settings.</span></span> <span data-ttu-id="a9c97-131">O valor padrão é uma aspa (").</span><span class="sxs-lookup"><span data-stu-id="a9c97-131">The default value is a quotation mark (").</span></span>|  
|`RecordDelimiter`|<span data-ttu-id="a9c97-132">O delimitador de registro a ser colocado no término de cada registro.</span><span class="sxs-lookup"><span data-stu-id="a9c97-132">The record delimiter to put at the end of each record.</span></span> <span data-ttu-id="a9c97-133">O valor padrão é \<cr>\<lf>.</span><span class="sxs-lookup"><span data-stu-id="a9c97-133">The default value is \<cr>\<lf>.</span></span>|  
|<span data-ttu-id="a9c97-134">**SuppressLineBreaks**</span><span class="sxs-lookup"><span data-stu-id="a9c97-134">**SuppressLineBreaks**</span></span>|<span data-ttu-id="a9c97-135">Indica se as quebras de linha serão removidas dos dados incluídos na saída.</span><span class="sxs-lookup"><span data-stu-id="a9c97-135">Indicates whether line breaks are removed from the data included in the output.</span></span> <span data-ttu-id="a9c97-136">O valor padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-136">The default value is `false`.</span></span> <span data-ttu-id="a9c97-137">Se o valor for `true`, as configurações `FieldDelimiter`, `RecordDelimiter`e `Qualifier` não poderão ser um caractere de espaço.</span><span class="sxs-lookup"><span data-stu-id="a9c97-137">If the value is `true`, the `FieldDelimiter`, `RecordDelimiter`, and `Qualifier` settings cannot be a space character.</span></span>|  
|`UseFormattedValues`|<span data-ttu-id="a9c97-138">Indica se as cadeias de caracteres formatadas são colocadas na saída do CSV.</span><span class="sxs-lookup"><span data-stu-id="a9c97-138">Indicates whether formatted strings are put into the CSV output.</span></span> <span data-ttu-id="a9c97-139">O valor padrão é `true` quando `ExcelMode` for `true`; caso contrário, ele será `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c97-139">The default value is `true` when `ExcelMode` is `true`; otherwise it is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9c97-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9c97-140">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="a9c97-141">[Passando configurações de informações de dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a9c97-141">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="a9c97-142">[Personalizar parâmetros de extensão de renderização no RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="a9c97-142">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="a9c97-143">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a9c97-143">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  