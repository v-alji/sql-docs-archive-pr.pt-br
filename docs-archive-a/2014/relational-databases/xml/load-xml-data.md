---
title: Carregar dados XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681452"
---
# <a name="load-xml-data"></a><span data-ttu-id="0d76c-102">Carregar dados XML</span><span class="sxs-lookup"><span data-stu-id="0d76c-102">Load XML Data</span></span>
  <span data-ttu-id="0d76c-103">É possível transferir dados XML para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="0d76c-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="0d76c-104">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d76c-104">For example:</span></span>  
  
-   <span data-ttu-id="0d76c-105">Se você tiver dados em uma coluna de imagem ou [n]text em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , poderá importar a tabela usando o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d76c-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0d76c-106">Altere o tipo da coluna para XML usando a instrução ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="0d76c-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="0d76c-107">É possível copiar os dados em massa de outro banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando bcp out e inserir os dados em massa no banco de dados da versão posterior usando bcp in.</span><span class="sxs-lookup"><span data-stu-id="0d76c-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="0d76c-108">Se você tiver dados em colunas relacionais em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , crie uma nova tabela com uma coluna [n]text e, opcionalmente, uma coluna de chave primária para um identificador de linha.</span><span class="sxs-lookup"><span data-stu-id="0d76c-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="0d76c-109">Use programação do lado do cliente para recuperar o XML gerado no servidor com FOR XML e gravá-la na coluna `[n]text`.</span><span class="sxs-lookup"><span data-stu-id="0d76c-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="0d76c-110">Em seguida, use as técnicas mencionadas anteriormente para transferir dados para um banco de dados de versão posterior.</span><span class="sxs-lookup"><span data-stu-id="0d76c-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="0d76c-111">É possível optar por gravar diretamente o XML em uma coluna XML no banco de dados da versão posterior.</span><span class="sxs-lookup"><span data-stu-id="0d76c-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="0d76c-112">Carregando dados XML em massa</span><span class="sxs-lookup"><span data-stu-id="0d76c-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="0d76c-113">É possível carregar dados XML em massa no servidor usando os recursos de carregamento em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como bcp.</span><span class="sxs-lookup"><span data-stu-id="0d76c-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="0d76c-114">O OPENROWSET permite carregar dados de arquivos em uma coluna de XML.</span><span class="sxs-lookup"><span data-stu-id="0d76c-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="0d76c-115">O exemplo a seguir ilustra esse ponto.</span><span class="sxs-lookup"><span data-stu-id="0d76c-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="0d76c-116">Exemplo: Carregando XML de arquivos</span><span class="sxs-lookup"><span data-stu-id="0d76c-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="0d76c-117">Este exemplo mostra como inserir uma linha na tabela T. O valor da coluna XML é carregado do arquivo C:\MyFile\xmlfile.xml como CLOB, e a coluna de inteiro recebe o valor 10.</span><span class="sxs-lookup"><span data-stu-id="0d76c-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="0d76c-118">Codificação de Texto</span><span class="sxs-lookup"><span data-stu-id="0d76c-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d76c-119">armazena dados XML em Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="0d76c-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="0d76c-120">Os dados XML recuperados do servidor são fornecidos em codificação UTF-16.</span><span class="sxs-lookup"><span data-stu-id="0d76c-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="0d76c-121">Para obter uma codificação diferente, você precisa executar a conversão necessária nos dados recuperados.</span><span class="sxs-lookup"><span data-stu-id="0d76c-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="0d76c-122">Às vezes, os dados XML podem estar em uma codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="0d76c-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="0d76c-123">Nesse caso, você precisará ter cuidado durante o carregamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="0d76c-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="0d76c-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d76c-124">For example:</span></span>  
  
-   <span data-ttu-id="0d76c-125">Se o texto XML estiver em Unicode (UCS-2, UTF-16), você poderá atribuí-lo a uma coluna, variável ou parâmetro XML sem nenhum problema.</span><span class="sxs-lookup"><span data-stu-id="0d76c-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="0d76c-126">Se a codificação não for Unicode e for implícita, por causa da página de código de origem, a página de código da cadeia de caracteres no banco de dados deverá ser igual ou compatível com os pontos de código que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="0d76c-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="0d76c-127">Se necessário, use COLLATE.</span><span class="sxs-lookup"><span data-stu-id="0d76c-127">If required, use COLLATE.</span></span> <span data-ttu-id="0d76c-128">Se não houver nenhuma página de código desse tipo, será necessário adicionar uma declaração XML explícita com a codificação correta.</span><span class="sxs-lookup"><span data-stu-id="0d76c-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="0d76c-129">Para usar uma codificação explícita, use o tipo `varbinary()`, que não tem nenhuma interação com páginas de código. ou use um tipo de cadeia de caracteres da página de código apropriada.</span><span class="sxs-lookup"><span data-stu-id="0d76c-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="0d76c-130">Em seguida, atribua os dados a uma coluna, variável ou parâmetro XML.</span><span class="sxs-lookup"><span data-stu-id="0d76c-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="0d76c-131">Exemplo: Especificando uma codificação explicitamente</span><span class="sxs-lookup"><span data-stu-id="0d76c-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="0d76c-132">Assuma que você tem um documento XML, vcdoc, armazenado como `varchar(max)` que não tem uma declaração XML explícita.</span><span class="sxs-lookup"><span data-stu-id="0d76c-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="0d76c-133">A instrução a seguir adiciona uma declaração XML com a codificação "iso8859-1", concatena o documento XML, converte o resultado em `varbinary(max)` de forma que a representação de bytes seja preservada e, finalmente, converte-o em XML.</span><span class="sxs-lookup"><span data-stu-id="0d76c-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="0d76c-134">Isso permite que o processador XML analise os dados de acordo com a codificação "iso8859-1" especificada e gere a representação UTF-16 correspondente para valores de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d76c-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="0d76c-135">Incompatibilidades de codificação de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0d76c-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="0d76c-136">Se você copiar e analisar XML como uma cadeia de caracteres literal na janela Editor de Consultas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], poderá experimentar incompatibilidades de codificação de cadeia de caracteres [N]VARCHAR.</span><span class="sxs-lookup"><span data-stu-id="0d76c-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="0d76c-137">Isso dependerá da codificação de sua instância XML.</span><span class="sxs-lookup"><span data-stu-id="0d76c-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="0d76c-138">Em muitas casos, você poderá desejar remover a declaração XML.</span><span class="sxs-lookup"><span data-stu-id="0d76c-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="0d76c-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d76c-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="0d76c-140">Você deve incluir um N para transformar a instância de XML em uma instância de Unicode.</span><span class="sxs-lookup"><span data-stu-id="0d76c-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="0d76c-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d76c-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d76c-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d76c-142">See Also</span></span>  
 [<span data-ttu-id="0d76c-143">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0d76c-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
