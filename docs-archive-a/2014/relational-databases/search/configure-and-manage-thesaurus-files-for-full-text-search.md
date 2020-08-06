---
title: Configurar e gerenciar arquivos de dicionário de sinônimos para Pesquisa de Texto Completo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686237"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="653a1-102">Configurar e gerenciar arquivos de dicionário de sinônimos para Pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="653a1-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="653a1-103">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as consultas de texto completo podem procurar sinônimos de termos especificados pelo usuário através do uso de um dicionário de sinônimos.</span><span class="sxs-lookup"><span data-stu-id="653a1-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="653a1-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *dicionário de sinônimos* define um conjunto de sinônimos para um idioma específico.</span><span class="sxs-lookup"><span data-stu-id="653a1-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="653a1-105">Os administradores de sistema podem definir duas formas de sinônimos: conjuntos de expansão e conjuntos de substituição.</span><span class="sxs-lookup"><span data-stu-id="653a1-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="653a1-106">Ao desenvolver um dicionário de sinônimos personalizado para seus dados de texto completo, você pode efetivamente ampliar o escopo de consultas de texto completo baseadas nesses dados.</span><span class="sxs-lookup"><span data-stu-id="653a1-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="653a1-107">A correspondência com o dicionário de sinônimos ocorre para todas as consultas [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) e [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) , e para quaisquer consultas [CONTAINS](/sql/t-sql/queries/contains-transact-sql) e [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) que especifiquem a cláusula FORMSOF THESAURUS.</span><span class="sxs-lookup"><span data-stu-id="653a1-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="653a1-108">Tarefas básicas para configurar um arquivo de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="653a1-109">Para que as consultas de pesquisa de texto completo na sua instância de servidor possam procurar sinônimos em um determinado idioma, defina mapeamentos de dicionário de sinônimos (sinônimos) para esse idioma.</span><span class="sxs-lookup"><span data-stu-id="653a1-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="653a1-110">Cada dicionário deve ser configurado manualmente para definir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="653a1-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="653a1-111">Configuração de diacríticos</span><span class="sxs-lookup"><span data-stu-id="653a1-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="653a1-112">Para um determinado dicionário de sinônimos, todos os padrões de pesquisa são confidenciais ou não sensíveis a marcas de sinais diacríticos, como til ( **~** ), acento agudo (**??**) ou trema (**??**) (ou seja, *diferencia acentos* ou não *diferencia acentos*).</span><span class="sxs-lookup"><span data-stu-id="653a1-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="653a1-113">Por exemplo, suponha que você especifique o padrão "CAF??"</span><span class="sxs-lookup"><span data-stu-id="653a1-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="653a1-114">a ser substituído por outros padrões em uma consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="653a1-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="653a1-115">Se o dicionário de sinônimos não diferenciar acentos, a pesquisa de texto completo substituirá os padrões "CAF??"</span><span class="sxs-lookup"><span data-stu-id="653a1-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="653a1-116">e "café".</span><span class="sxs-lookup"><span data-stu-id="653a1-116">and "cafe".</span></span> <span data-ttu-id="653a1-117">Se o dicionário de sinônimos diferenciar acentos, a pesquisa de texto completo substituirá apenas o padrão "CAF??".</span><span class="sxs-lookup"><span data-stu-id="653a1-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="653a1-118">Por padrão, um dicionário de sinônimos não diferencia acentos.</span><span class="sxs-lookup"><span data-stu-id="653a1-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="653a1-119">Conjunto de expansão</span><span class="sxs-lookup"><span data-stu-id="653a1-119">Expansion set</span></span>  
  
     <span data-ttu-id="653a1-120">Um conjunto de expansão contém um grupo de sinônimos, como "escritor", "autor" e "jornalista", que são substituídos entre si por uma consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="653a1-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="653a1-121">As consultas que contêm uma correspondência para qualquer sinônimo do conjunto de expansão são expandidas para incluir todos os outros sinônimos do conjunto de expansão.</span><span class="sxs-lookup"><span data-stu-id="653a1-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="653a1-122">Para obter mais informações, consulte "Estrutura XML de um conjunto de expansão", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="653a1-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="653a1-123">Conjunto de substituição</span><span class="sxs-lookup"><span data-stu-id="653a1-123">Replacement set</span></span>  
  
     <span data-ttu-id="653a1-124">Um conjunto de substituição contém um padrão de texto a ser substituído por um conjunto de substituição.</span><span class="sxs-lookup"><span data-stu-id="653a1-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="653a1-125">Para ver um exemplo, consulte a seção "Estrutura XML de um conjunto de substituição" posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="653a1-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="653a1-126">Conteúdo inicial dos arquivos do dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="653a1-127">oferece um conjunto de arquivos XML de dicionário de sinônimos, um para cada idioma com suporte.</span><span class="sxs-lookup"><span data-stu-id="653a1-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="653a1-128">Esses arquivos estão basicamente vazios.</span><span class="sxs-lookup"><span data-stu-id="653a1-128">These files are essentially empty.</span></span> <span data-ttu-id="653a1-129">Eles contêm apenas a estrutura XML de alto nível que é comum a todos os dicionários de sinônimos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e um dicionário de sinônimos de exemplo comentado.</span><span class="sxs-lookup"><span data-stu-id="653a1-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="653a1-130">Todos os arquivos de dicionário de sinônimos fornecidos com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contêm o seguinte código XML:</span><span class="sxs-lookup"><span data-stu-id="653a1-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="653a1-131">Local dos arquivos do dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="653a1-132">A localização padrão dos arquivos de dicionário de sinônimos é esta:</span><span class="sxs-lookup"><span data-stu-id="653a1-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="653a1-133">*<SQL_Server_data_files_path>* \MSSQL12. MSSQLSERVER\MSSQL\FTDATA</span><span class="sxs-lookup"><span data-stu-id="653a1-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="653a1-134">Esse local padrão contém os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="653a1-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="653a1-135">Arquivos de dicionário de sinônimos específicos de um idioma</span><span class="sxs-lookup"><span data-stu-id="653a1-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="653a1-136">Durante a instalação, arquivos vazios do dicionário de sinônimos são instalados no local indicado acima.</span><span class="sxs-lookup"><span data-stu-id="653a1-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="653a1-137">Um arquivo à parte é fornecido para cada idioma suportado.</span><span class="sxs-lookup"><span data-stu-id="653a1-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="653a1-138">Um administrador de sistema pode personalizar esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="653a1-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="653a1-139">Os nomes de arquivo padrão dos arquivos de dicionário de sinônimos usam o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="653a1-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="653a1-140">' ts ' + \<three-letter language-abbreviation> + '. xml '</span><span class="sxs-lookup"><span data-stu-id="653a1-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="653a1-141">O nome do arquivo de dicionário de sinônimos de um idioma é especificado no Registro no seguinte valor: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<nome-da-instância>\MSSearch\\<abreviação-do-idioma>.</span><span class="sxs-lookup"><span data-stu-id="653a1-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="653a1-142">O arquivo de dicionário de sinônimos global</span><span class="sxs-lookup"><span data-stu-id="653a1-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="653a1-143">Um arquivo de dicionário de sinônimos global vazio, tsGlobal.xml.</span><span class="sxs-lookup"><span data-stu-id="653a1-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="653a1-144">Você pode alterar a localização e os nomes de um arquivo de dicionário de sinônimos mudando a respectiva chave do Registro.</span><span class="sxs-lookup"><span data-stu-id="653a1-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="653a1-145">Para cada idioma, a localização do arquivo de dicionário de sinônimos é especificada no seguinte valor do Registro:</span><span class="sxs-lookup"><span data-stu-id="653a1-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="653a1-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/ \<instance name> /MSSearch/Language/ \<language-abbreviation> /TsaurusFile</span><span class="sxs-lookup"><span data-stu-id="653a1-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="653a1-147">O arquivo de dicionário de sinônimos global corresponde ao idioma Neutro com LCID 0.</span><span class="sxs-lookup"><span data-stu-id="653a1-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="653a1-148">Esse valor só pode ser alterado por administradores.</span><span class="sxs-lookup"><span data-stu-id="653a1-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="653a1-149">Como as consultas usam arquivos de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="653a1-150">Uma consulta ao dicionário de sinônimos usa um dicionário de sinônimos específico de um idioma e o dicionário de sinônimos global.</span><span class="sxs-lookup"><span data-stu-id="653a1-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="653a1-151">Primeiro, a consulta pesquisa pelo arquivo específico do idioma e depois o carrega para ser processado (a menos que já esteja carregado).</span><span class="sxs-lookup"><span data-stu-id="653a1-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="653a1-152">A consulta é expandida para incluir os sinônimos específicos do idioma definidos pelos conjuntos de expansão e regras de substituição no arquivo do dicionário de sinônimos.</span><span class="sxs-lookup"><span data-stu-id="653a1-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="653a1-153">Essas etapas são repetidas para o dicionário de sinônimos global.</span><span class="sxs-lookup"><span data-stu-id="653a1-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="653a1-154">Entretanto, se um termo já tiver correspondências no arquivo de dicionário de sinônimos específico do idioma, ele não terá correspondentes no dicionário de sinônimos global.</span><span class="sxs-lookup"><span data-stu-id="653a1-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="653a1-155">Compreendendo a estrutura de um arquivo de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="653a1-156">Cada arquivo de dicionário de sinônimos define um contêiner XML cuja ID é `Microsoft Search Thesaurus`, além de um comentário, `<!--` ... `-->`, que contém um dicionário de sinônimos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="653a1-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="653a1-157">O dicionário de sinônimos é definido em um \<thesaurus> elemento que contém exemplos dos elementos filho que definem a configuração de diacríticos, os conjuntos de expansão e os conjuntos de substituição, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="653a1-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="653a1-158">Estrutura XML da configuração de diacríticos</span><span class="sxs-lookup"><span data-stu-id="653a1-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="653a1-159">A configuração de diacríticos de um dicionário de sinônimos é especificada em um único elemento <diacritics_sensitive>.</span><span class="sxs-lookup"><span data-stu-id="653a1-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="653a1-160">Esse elemento contém um valor de inteiro que controla a distinção de acentos, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="653a1-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="653a1-161">Configuração de diacríticos</span><span class="sxs-lookup"><span data-stu-id="653a1-161">Diacritics Setting</span></span>|<span data-ttu-id="653a1-162">Valor</span><span class="sxs-lookup"><span data-stu-id="653a1-162">Value</span></span>|<span data-ttu-id="653a1-163">XML</span><span class="sxs-lookup"><span data-stu-id="653a1-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="653a1-164">não diferenciam acentos</span><span class="sxs-lookup"><span data-stu-id="653a1-164">Accent insensitive</span></span>|<span data-ttu-id="653a1-165">0</span><span class="sxs-lookup"><span data-stu-id="653a1-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="653a1-166">diferenciam acentos</span><span class="sxs-lookup"><span data-stu-id="653a1-166">Accent sensitive</span></span>|<span data-ttu-id="653a1-167">1</span><span class="sxs-lookup"><span data-stu-id="653a1-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="653a1-168">Essa configuração só pode ser aplicada uma vez no arquivo e é válida para todos os padrões de pesquisa do arquivo.</span><span class="sxs-lookup"><span data-stu-id="653a1-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="653a1-169">Essa configuração não pode ser especificada para padrões individuais.</span><span class="sxs-lookup"><span data-stu-id="653a1-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="653a1-170">Estrutura XML de um conjunto de expansão</span><span class="sxs-lookup"><span data-stu-id="653a1-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="653a1-171">Cada conjunto de expansão é incluído em um elemento \<expansion>.</span><span class="sxs-lookup"><span data-stu-id="653a1-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="653a1-172">Nesse elemento, você especifica uma ou mais substituições em um elemento \<sub>.</span><span class="sxs-lookup"><span data-stu-id="653a1-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="653a1-173">No conjunto de expansão, você pode especificar um grupo de substituições sinônimas umas das outras.</span><span class="sxs-lookup"><span data-stu-id="653a1-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="653a1-174">Por exemplo, você pode editar a seção de expansão para tratar as substituições "escritor", "autor" e "jornalista" como sinônimos.</span><span class="sxs-lookup"><span data-stu-id="653a1-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="653a1-175">As consultas de pesquisa de texto completo que contêm correspondências em uma substituição são expandidas para incluir todas as outras substituições especificadas no conjunto de expansão.</span><span class="sxs-lookup"><span data-stu-id="653a1-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="653a1-176">Por isso, no exemplo anterior, quando você emite uma consulta FORMS OF THESAURUS ou FREETEXT para a palavra "autor", a pesquisa de texto completo também retorna resultados que contêm as palavras "escritor" e "jornalista".</span><span class="sxs-lookup"><span data-stu-id="653a1-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="653a1-177">A seção de conjuntos de expansão do exemplo anterior seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="653a1-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="653a1-178">Estrutura XML de um conjunto de substituição</span><span class="sxs-lookup"><span data-stu-id="653a1-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="653a1-179">Cada conjunto de substituição é incluído em um elemento \<replacement>.</span><span class="sxs-lookup"><span data-stu-id="653a1-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="653a1-180">Nesse elemento, é possível especificar um ou mais padrões em um elemento \<pat> e zero ou mais substituições em elementos \<sub>, um por sinônimo.</span><span class="sxs-lookup"><span data-stu-id="653a1-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="653a1-181">Também pode especificar um padrão a ser substituído por um conjunto de substituição.</span><span class="sxs-lookup"><span data-stu-id="653a1-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="653a1-182">Padrões e substituições podem conter uma palavra ou uma sequência de palavras.</span><span class="sxs-lookup"><span data-stu-id="653a1-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="653a1-183">Se não houver uma substituição especificada para um padrão, isso será o mesmo que remover o padrão da consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="653a1-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="653a1-184">Por exemplo, vamos supor que você deseja que as consultas relacionadas ao termo "Win8", o padrão, sejam substituídas por "Windows Server 2012" ou "Windows 8.0", as substituições.</span><span class="sxs-lookup"><span data-stu-id="653a1-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="653a1-185">Se você executar uma consulta de texto completo usando o termo "Win8", a pesquisa de texto completo retornará apenas resultados que contenham "Windows Server 2012" ou "Windows 8.0",</span><span class="sxs-lookup"><span data-stu-id="653a1-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="653a1-186">e não resultados que contenham "Win8".</span><span class="sxs-lookup"><span data-stu-id="653a1-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="653a1-187">Isso acontece porque o padrão "Win8" foi “substituído” pelos padrões "Windows Server 2012" e "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="653a1-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="653a1-188">A seção de conjuntos de substituição procuraria o seguinte para o exemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="653a1-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="653a1-189">Se você tiver dois conjuntos de substituição com padrões semelhantes sendo associados, o mais longo dos dois tem precedência.</span><span class="sxs-lookup"><span data-stu-id="653a1-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="653a1-190">Por exemplo, ao executar a consulta FORMS OF THESAURUS para "comunidade online do Internet Explorer" com os conjuntos de substituição a seguir, o conjunto de substituição "Internet Explorer" tem precedência sobre o conjunto de substituição "Internet".</span><span class="sxs-lookup"><span data-stu-id="653a1-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="653a1-191">Portanto, essa consulta será processada como "comunidade online do IE" ou "comunidade online do IE 9".</span><span class="sxs-lookup"><span data-stu-id="653a1-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="653a1-192">e</span><span class="sxs-lookup"><span data-stu-id="653a1-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="653a1-193">Trabalhando com arquivos de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="653a1-194">**Para editar um arquivo de dicionário de sinônimos**</span><span class="sxs-lookup"><span data-stu-id="653a1-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="653a1-195">Editando um arquivo de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="653a1-196">**Para carregar um arquivo de dicionário de sinônimos atualizado**</span><span class="sxs-lookup"><span data-stu-id="653a1-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="653a1-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="653a1-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="653a1-198">**Para exibir o resultado da geração de tokens de um separador de palavras, dicionário de sinônimos e combinação de lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="653a1-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="653a1-199">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="653a1-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="653a1-200">Editando um arquivo de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="653a1-201">É possível configurar o dicionário de sinônimos de um idioma editando seu arquivo (um arquivo XML).</span><span class="sxs-lookup"><span data-stu-id="653a1-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="653a1-202">Durante a instalação, os arquivos de dicionário de sinônimos vazios que contêm apenas o \<xml> contêiner e um elemento de exemplo comentado \<thesaurus> são instalados.</span><span class="sxs-lookup"><span data-stu-id="653a1-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="653a1-203">Para que as consultas de pesquisa de texto completo que procuram sinônimos funcionem corretamente, você deve criar um \<thesaurus> elemento real que defina um conjunto de sinônimos.</span><span class="sxs-lookup"><span data-stu-id="653a1-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="653a1-204">Você pode definir duas formas de sinônimos: conjuntos de expansão e conjuntos de substituição.</span><span class="sxs-lookup"><span data-stu-id="653a1-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="653a1-205">**Restrições para arquivos de dicionário de sinônimos**</span><span class="sxs-lookup"><span data-stu-id="653a1-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="653a1-206">As seguintes restrições se aplicam à edição de um arquivo de dicionário de sinônimos:</span><span class="sxs-lookup"><span data-stu-id="653a1-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="653a1-207">Somente administradores do sistema podem atualizar, modificar ou excluir arquivos de dicionário de sinônimos.</span><span class="sxs-lookup"><span data-stu-id="653a1-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="653a1-208">Ao editar arquivos de dicionários de sinônimos usando ferramentas de editores de texto, é necessário salvá-los no formato Unicode e especificar Marcas de Ordem de Byte.</span><span class="sxs-lookup"><span data-stu-id="653a1-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="653a1-209">As entradas de dicionário de sinônimos não podem estar vazias, nem pode haver separação de palavras para uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="653a1-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="653a1-210">As frases no arquivo de dicionário de sinônimos não devem ter mais de 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="653a1-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="653a1-211">Um dicionário de sinônimos não deve conter entradas duplicadas entre as entradas \<sub> de conjuntos de expansão e os elementos \<pat> de conjuntos de substituição.</span><span class="sxs-lookup"><span data-stu-id="653a1-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="653a1-212">**Recomendações para arquivos de dicionário de sinônimos**</span><span class="sxs-lookup"><span data-stu-id="653a1-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="653a1-213">Recomendamos que as entradas no arquivo do dicionário de sinônimos não contenham caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="653a1-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="653a1-214">Isso ocorre porque os separadores de palavras têm comportamentos sutis em relação a caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="653a1-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="653a1-215">Se uma entrada de dicionário de sinônimos contiver caracteres especiais, os separadores de palavras usados com essa entrada poderão ter implicações de comportamento sutis para uma consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="653a1-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="653a1-216">Recomendamos que as entradas \<sub> não contenham palavras irrelevantes, pois tais palavras são omitidas do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="653a1-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="653a1-217">As consultas são expandidas para incluir as entradas \<sub> de um arquivo de dicionário de sinônimos e, se uma entrada \<sub> contiver palavras irrelevantes, o tamanho da consulta aumentará desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="653a1-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="653a1-218">Para editar um arquivo de dicionário de sinônimos</span><span class="sxs-lookup"><span data-stu-id="653a1-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="653a1-219">Abra o arquivo de dicionário de sinônimos no Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="653a1-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="653a1-220">Se você estiver editando um arquivo de dicionário de sinônimos pela primeira vez, remova as seguintes linhas de comentário no início e final do arquivo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="653a1-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="653a1-221">Adicione, modifique ou exclua um conjunto de substituições ou conjunto de expansão.</span><span class="sxs-lookup"><span data-stu-id="653a1-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="653a1-222">Salve o arquivo e feche o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="653a1-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="653a1-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) para carregar o conteúdo do arquivo de dicionário de sinônimos no tempdb, especificando o LCID (identificador de localidade) correspondente ao idioma do arquivo.</span><span class="sxs-lookup"><span data-stu-id="653a1-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="653a1-224">Por exemplo, para o arquivo de dicionário de sinônimos em inglês, tsenu.xml, o LCID correspondente é 1033.</span><span class="sxs-lookup"><span data-stu-id="653a1-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="653a1-225">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="653a1-225">See Also</span></span>  
 <span data-ttu-id="653a1-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="653a1-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="653a1-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="653a1-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="653a1-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="653a1-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="653a1-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="653a1-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="653a1-230">Pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="653a1-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
