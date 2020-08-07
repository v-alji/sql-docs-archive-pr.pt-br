---
title: Importar dados de formato de caractere e nativos de versões anteriores do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576380"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="71241-102">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="71241-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="71241-103">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], você pode usar o **bcp** para importar dados de formato de caractere e nativo do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] usando a opção **-V** .</span><span class="sxs-lookup"><span data-stu-id="71241-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="71241-104">A opção **-V** faz com que o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] use tipos de dados da versão anterior especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e o formato de arquivo de dados é igual ao formato da versão anterior.</span><span class="sxs-lookup"><span data-stu-id="71241-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="71241-105">Para especificar uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados, use a opção **-V** com os seguintes qualificadores:</span><span class="sxs-lookup"><span data-stu-id="71241-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="71241-106">Versão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="71241-106">SQL Server version</span></span>|<span data-ttu-id="71241-107">Qualificador</span><span class="sxs-lookup"><span data-stu-id="71241-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="71241-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="71241-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="71241-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="71241-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="71241-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="71241-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="71241-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="71241-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="71241-112">Interpretação de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="71241-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="71241-113">e versões posteriores oferecem suporte para alguns novos tipos.</span><span class="sxs-lookup"><span data-stu-id="71241-113">and later versions have support for some new types.</span></span> <span data-ttu-id="71241-114">Para importar um novo tipo de dados para uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o tipo de dados deve ser armazenado em um formato legível pelos clientes **bcp** antigos.</span><span class="sxs-lookup"><span data-stu-id="71241-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="71241-115">A tabela a seguir resume como os novos tipos de dados são convertidos para compatibilidade com versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71241-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="71241-116">Novos tipos de dados no SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="71241-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="71241-117">Tipos de dados compatíveis na versão 6*x*</span><span class="sxs-lookup"><span data-stu-id="71241-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="71241-118">Tipos de dados compatíveis na versão 70</span><span class="sxs-lookup"><span data-stu-id="71241-118">Compatible data types in version 70</span></span>|<span data-ttu-id="71241-119">Tipos de dados compatíveis na versão 80</span><span class="sxs-lookup"><span data-stu-id="71241-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="71241-120">XML</span><span class="sxs-lookup"><span data-stu-id="71241-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="71241-121">UDT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="71241-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="71241-122">\*Esse tipo tem suporte nativo.</span><span class="sxs-lookup"><span data-stu-id="71241-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="71241-123"><sup>1</sup> UDT indica um tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="71241-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="71241-124">Exportar usando – V 80</span><span class="sxs-lookup"><span data-stu-id="71241-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="71241-125">Quando você exporta dados em massa usando a opção **-V80** , `nvarchar(max)` ,,, `varchar(max)` `varbinary(max)` XML e dados UDT no modo nativo são armazenados com um prefixo de 4 bytes, como `text` , `image` e `ntext` dados, em vez de um prefixo de 8 bytes, que é o padrão para o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="71241-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="71241-126">Copiando valores de dados</span><span class="sxs-lookup"><span data-stu-id="71241-126">Copying Date Values</span></span>  
 <span data-ttu-id="71241-127">O**bcp** usa a API de cópia em massa do ODBC.</span><span class="sxs-lookup"><span data-stu-id="71241-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="71241-128">Portanto, para importar valores de data para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o **bcp** usa o formato de data do ODBC (*yyyy-mm-dd hh:mm:ss*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="71241-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="71241-129">O comando **bcp** exporta arquivos de dados de formato de caractere usando o formato padrão ODBC para `datetime` `smalldatetime` valores e.</span><span class="sxs-lookup"><span data-stu-id="71241-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="71241-130">Por exemplo, uma coluna `datetime` que contém a data `12 Aug 1998` é copiada em massa em um arquivo de dados como a cadeia de caracteres `1998-08-12 00:00:00.000`.</span><span class="sxs-lookup"><span data-stu-id="71241-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71241-131">Ao importar dados para um `smalldatetime` campo usando **bcp**, certifique-se de que o valor de segundos seja 0, 0; caso contrário, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="71241-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="71241-132">O tipo de dados `smalldatetime` só mantém valores do minuto mais próximo.</span><span class="sxs-lookup"><span data-stu-id="71241-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="71241-133">BULK INSERT e INSERT ... SELECT \* FROM OPENROWSET(BULK...) não falharão nesta instância, mas truncarão o valor de segundos.</span><span class="sxs-lookup"><span data-stu-id="71241-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="71241-134">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="71241-134">Related Tasks</span></span>  
 <span data-ttu-id="71241-135">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="71241-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="71241-136">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71241-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="71241-137">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71241-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="71241-138">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71241-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="71241-139">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71241-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="71241-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71241-140">See Also</span></span>  
 <span data-ttu-id="71241-141">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="71241-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="71241-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71241-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="71241-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71241-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="71241-144">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71241-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="71241-145">[Compatibilidade com versões anteriores do Mecanismo de Banco de Dados do SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="71241-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="71241-146">CAST e CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71241-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
