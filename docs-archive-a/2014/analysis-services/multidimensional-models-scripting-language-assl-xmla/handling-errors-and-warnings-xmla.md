---
title: Tratamento de erros e avisos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572778"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="2fdb4-102">Manipulando erros e avisos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="2fdb4-103">O tratamento de erros é necessário quando uma chamada de método [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) ou [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) de XML for Analysis (XMLA) não é executada, é executada com êxito, mas gera erros ou avisos ou é executada com êxito, mas retorna resultados que contêm erros.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="2fdb4-104">Erro</span><span class="sxs-lookup"><span data-stu-id="2fdb4-104">Error</span></span>|<span data-ttu-id="2fdb4-105">Relatório</span><span class="sxs-lookup"><span data-stu-id="2fdb4-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="2fdb4-106">A chamada de método XMLA não é executada</span><span class="sxs-lookup"><span data-stu-id="2fdb4-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="2fdb4-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna uma mensagem de falha SOAP que contém os detalhes da falha.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="2fdb4-108">Para obter mais informações, consulte a seção [manipulando falhas de SOAP](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="2fdb4-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="2fdb4-109">Erros ou avisos em uma chamada de método com êxito</span><span class="sxs-lookup"><span data-stu-id="2fdb4-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="2fdb4-110">inclui um elemento [Error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) ou [Warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) para cada erro ou aviso, respectivamente, na propriedade [messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) do elemento [raiz](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) que contém os resultados da chamada de método.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="2fdb4-111">Para obter mais informações, consulte a seção [Manipulando erros e avisos](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="2fdb4-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="2fdb4-112">Erros no resultado de uma chamada de método com êxito</span><span class="sxs-lookup"><span data-stu-id="2fdb4-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="2fdb4-113">inclui um elemento embutido `error` ou `warning` para o erro ou aviso, respectivamente, dentro da [célula](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) ou elemento de [linha](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) apropriado dos resultados da chamada de método.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="2fdb4-114">Para obter mais informações, consulte a seção [Manipulando erros e avisos embutidos](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="2fdb4-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="2fdb4-115">Manipulando falhas de SOAP</span><span class="sxs-lookup"><span data-stu-id="2fdb4-115">Handling SOAP Faults</span></span>  
 <span data-ttu-id="2fdb4-116">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna uma falha SOAP quando ocorrem as seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="2fdb4-116">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="2fdb4-117">A mensagem SOAP que contém o método XMLA não foi bem formada ou não pôde ser validada pela instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fdb4-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="2fdb4-118">Houve um erro de comunicação ou outro erro envolvendo a mensagem SOAP que contém o método XMLA.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="2fdb4-119">O método XMLA não foi executado na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fdb4-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="2fdb4-120">Os códigos de falha SOAP para XMLstartA começam com "XMLForAnalysis", seguido por um ponto e o código de resultado hexadecimal HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="2fdb4-121">Por exemplo, um código de erro "`0x80000005`" é formatado como "`XMLForAnalysis.0x80000005`".</span><span class="sxs-lookup"><span data-stu-id="2fdb4-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="2fdb4-122">Para obter mais informações sobre o formato de falha SOAP, consulte Falha Soap no protocolo SOAP 1.1 do W3C.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="2fdb4-123">Informações de código de falha</span><span class="sxs-lookup"><span data-stu-id="2fdb4-123">Fault Code Information</span></span>  
 <span data-ttu-id="2fdb4-124">A tabela a seguir mostra as informações de código de falha XMLA contidas na sessão de detalhe da resposta SOAP.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="2fdb4-125">As colunas são os atributos de um erro na seção de detalhe de uma falha SOAP.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="2fdb4-126">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="2fdb4-126">Column name</span></span>|<span data-ttu-id="2fdb4-127">Type</span><span class="sxs-lookup"><span data-stu-id="2fdb4-127">Type</span></span>|<span data-ttu-id="2fdb4-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fdb4-128">Description</span></span>|<span data-ttu-id="2fdb4-129">Nulo permitido<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2fdb4-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="2fdb4-130">Código de retorno que indica o êxito ou a falha do método.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="2fdb4-131">O valor hexadecimal deve ser convertido para um valor `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="2fdb4-132">Não</span><span class="sxs-lookup"><span data-stu-id="2fdb4-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="2fdb4-133">Código de retorno que indica uma condição de aviso.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="2fdb4-134">O valor hexadecimal deve ser convertido para um valor `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="2fdb4-135">Sim</span><span class="sxs-lookup"><span data-stu-id="2fdb4-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="2fdb4-136">Texto e descrição de erro ou de aviso retornadas pelo componente que gerou o erro.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="2fdb4-137">Sim</span><span class="sxs-lookup"><span data-stu-id="2fdb4-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="2fdb4-138">Nome do componente que gerou o erro ou o aviso.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="2fdb4-139">Sim</span><span class="sxs-lookup"><span data-stu-id="2fdb4-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="2fdb4-140">Caminho ou URL para o arquivo de Ajuda ou tópico que descreve o erro ou o aviso.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="2fdb4-141">Sim</span><span class="sxs-lookup"><span data-stu-id="2fdb4-141">Yes</span></span>|  
  
 <span data-ttu-id="2fdb4-142"><sup>1</sup> indica se os dados são obrigatórios e devem ser retornados, ou se os dados são opcionais, e se a coluna não se aplica.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="2fdb4-143">A seguir, um exemplo de uma falha SOAP ocorrida quando uma chamada de método falhou:</span><span class="sxs-lookup"><span data-stu-id="2fdb4-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="2fdb4-144">Manipulando erros e avisos</span><span class="sxs-lookup"><span data-stu-id="2fdb4-144">Handling Errors and Warnings</span></span>  
 <span data-ttu-id="2fdb4-145">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retornará a propriedade `Messages` no elemento `root` para um comando se as situações a seguir ocorrerem após a execução do comando:</span><span class="sxs-lookup"><span data-stu-id="2fdb4-145">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="2fdb4-146">O próprio método não falhou, mas houve uma falha na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] após o êxito da chamada de método.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="2fdb4-147">A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna um aviso quando o comando tem êxito.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="2fdb4-148">A propriedade `Messages` segue todas as outras propriedades contidas pelo elemento `root` e pode conter um ou mais elementos `Message`.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="2fdb4-149">Por sua vez, cada elemento `Message` pode conter um único elemento `error` ou `warning` descrevendo erros ou avisos, respectivamente, ocorridos para o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="2fdb4-150">Para obter mais informações sobre erros e avisos contidos na `Messages` propriedade, consulte [elemento messages &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="2fdb4-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="2fdb4-151">Manipulando erros durante a serialização</span><span class="sxs-lookup"><span data-stu-id="2fdb4-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="2fdb4-152">Se ocorrer um erro depois que a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instância já tiver começado a serializar a saída de um comando de execução bem-sucedida, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retornará um elemento de [exceção](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) em um namespace diferente no ponto do erro.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="2fdb4-153">A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fechará todos os elementos abertos para que o documento XML enviado ao cliente seja um documento válido.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="2fdb4-154">A instância também retornará um elemento `Messages` com a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="2fdb4-155">Manipulando erros e avisos embutidos</span><span class="sxs-lookup"><span data-stu-id="2fdb4-155">Handling Inline Errors and Warnings</span></span>  
 <span data-ttu-id="2fdb4-156">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retornará um `error` ou `warning` embutido para um comando se o próprio método XMLA não tenha falhado, mas houve um erro específico de um elemento de dados nos resultados retornados pelo método na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] após o êxito da chamada de método XMLA.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-156">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="2fdb4-157">fornece elementos embutidos `error` e `warning` se problemas específicos a uma célula ou a outros dados contidos em um `root` elemento usando o tipo de dados [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) ocorrem, como um erro de segurança ou erro de formatação para uma célula.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="2fdb4-158">Nesses casos, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna um elemento `error` ou `warning` no elemento `Cell` ou `row` que contém o erro ou o aviso, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="2fdb4-159">O exemplo a seguir ilustra um conjunto de resultados que contém um erro no conjunto de linhas retornado de um `Execute` método usando o comando de [instrução](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="2fdb4-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fdb4-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fdb4-160">See Also</span></span>  
 [<span data-ttu-id="2fdb4-161">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2fdb4-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
