---
title: Recuperar e consultar dados XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679731"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="2b47c-102">Recuperar e consultar dados XML</span><span class="sxs-lookup"><span data-stu-id="2b47c-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="2b47c-103">Este tópico descreve as opções de consulta que você tem que especificar para consultar dados XML.</span><span class="sxs-lookup"><span data-stu-id="2b47c-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="2b47c-104">Também descreve as partes de instâncias XML que não são preservadas quando são armazenadas em bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="2b47c-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="2b47c-105">Recursos de uma Instância XML que não são preservados</span><span class="sxs-lookup"><span data-stu-id="2b47c-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2b47c-106">preserva o conteúdo da instância XML, mas não preserva aspectos da instância XML que não são considerados significativos no modelo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="2b47c-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="2b47c-107">Isso significa que uma instância XML recuperada pode não ser idêntica à instância que foi armazenada no servidor, mas conterá as mesmas informações.</span><span class="sxs-lookup"><span data-stu-id="2b47c-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="2b47c-108">Declaração XML</span><span class="sxs-lookup"><span data-stu-id="2b47c-108">XML Declaration</span></span>  
 <span data-ttu-id="2b47c-109">A declaração XML em uma instância não é preservada quando a instância é armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b47c-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="2b47c-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b47c-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="2b47c-111">O resultado é `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="2b47c-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="2b47c-112">A declaração XML, como `<?xml version='1.0'?>`, não é preservada ao armazenar dados XML em uma instância de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="2b47c-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="2b47c-113">Isso ocorre por design.</span><span class="sxs-lookup"><span data-stu-id="2b47c-113">This is by design.</span></span> <span data-ttu-id="2b47c-114">A declaração XML () e seus atributos (versão/codificação/autônoma) são perdidos depois que os dados são convertidos no tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="2b47c-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="2b47c-115">A declaração XML é tratada como uma diretiva para o analisador XML.</span><span class="sxs-lookup"><span data-stu-id="2b47c-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="2b47c-116">Os dados XML são armazenados internamente como ucs-2.</span><span class="sxs-lookup"><span data-stu-id="2b47c-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="2b47c-117">Todos os outros PIs na instância XML são preservados.</span><span class="sxs-lookup"><span data-stu-id="2b47c-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="2b47c-118">Ordem dos atributos</span><span class="sxs-lookup"><span data-stu-id="2b47c-118">Order of Attributes</span></span>  
 <span data-ttu-id="2b47c-119">A ordem dos atributos em uma instância XML não é preservada.</span><span class="sxs-lookup"><span data-stu-id="2b47c-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="2b47c-120">Quando você consulta a instância XML armazenada na coluna de tipo `xml`, a ordem dos atributos no XML resultante pode ser diferente da instância XML original.</span><span class="sxs-lookup"><span data-stu-id="2b47c-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="2b47c-121">Aspas em torno de valores de atributos</span><span class="sxs-lookup"><span data-stu-id="2b47c-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="2b47c-122">Aspas simples e aspas duplas em torno de valores de atributos não são preservadas.</span><span class="sxs-lookup"><span data-stu-id="2b47c-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="2b47c-123">Os valores de atributos são armazenados no banco de dados como um nome e par de valores.</span><span class="sxs-lookup"><span data-stu-id="2b47c-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="2b47c-124">As aspas não são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="2b47c-124">The quotation marks are not stored.</span></span> <span data-ttu-id="2b47c-125">Quando uma XQuery é executada em uma instância XML, o XML resultante é serializado com aspas duplas em torno dos valores dos atributos.</span><span class="sxs-lookup"><span data-stu-id="2b47c-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="2b47c-126">As duas consultas retornam = `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="2b47c-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="2b47c-127">Prefixos de namespace</span><span class="sxs-lookup"><span data-stu-id="2b47c-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="2b47c-128">Prefixos de namespace não são preservados.</span><span class="sxs-lookup"><span data-stu-id="2b47c-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="2b47c-129">Quando você especifica XQuery em uma coluna de tipo `xml`, o resultado de XML serializado pode retornar prefixos de namespace diferentes.</span><span class="sxs-lookup"><span data-stu-id="2b47c-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="2b47c-130">O prefixo de namespace no resultado pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="2b47c-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="2b47c-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b47c-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="2b47c-132">A configuração solicitou opções de consulta</span><span class="sxs-lookup"><span data-stu-id="2b47c-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="2b47c-133">Ao consultar `xml` colunas de tipo ou variáveis usando `xml` métodos de tipo de dados, as opções a seguir devem ser definidas como mostrado.</span><span class="sxs-lookup"><span data-stu-id="2b47c-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="2b47c-134">Opções SET</span><span class="sxs-lookup"><span data-stu-id="2b47c-134">SET Options</span></span>|<span data-ttu-id="2b47c-135">Valores necessários</span><span class="sxs-lookup"><span data-stu-id="2b47c-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="2b47c-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="2b47c-136">ANSI_NULLS</span></span>|<span data-ttu-id="2b47c-137">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-137">ON</span></span>|  
|<span data-ttu-id="2b47c-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="2b47c-138">ANSI_PADDING</span></span>|<span data-ttu-id="2b47c-139">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-139">ON</span></span>|  
|<span data-ttu-id="2b47c-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="2b47c-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="2b47c-141">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-141">ON</span></span>|  
|<span data-ttu-id="2b47c-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="2b47c-142">ARITHABORT</span></span>|<span data-ttu-id="2b47c-143">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-143">ON</span></span>|  
|<span data-ttu-id="2b47c-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="2b47c-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="2b47c-145">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-145">ON</span></span>|  
|<span data-ttu-id="2b47c-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="2b47c-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="2b47c-147">OFF</span><span class="sxs-lookup"><span data-stu-id="2b47c-147">OFF</span></span>|  
|<span data-ttu-id="2b47c-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="2b47c-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="2b47c-149">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="2b47c-149">ON</span></span>|  
  
 <span data-ttu-id="2b47c-150">Se as opções não estiverem definidas como mostrado, as consultas e modificações nos `xml` métodos de tipo de dados falharão.</span><span class="sxs-lookup"><span data-stu-id="2b47c-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="2b47c-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b47c-151">See Also</span></span>  
 [<span data-ttu-id="2b47c-152">Criar instâncias de dados XML</span><span class="sxs-lookup"><span data-stu-id="2b47c-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
