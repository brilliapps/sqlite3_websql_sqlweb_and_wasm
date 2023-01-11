# sqlite3_websql_sqlweb_and_wasm
The aim ot this raw code library is to automatically enable you to use SQL in your browser regardles sql engine you are going to use or is available in your browser, f.e. Firefox cannot use websql, which chrome still can.
Take care to include from the sqlweb repo: https://github.com/ujjwalguptaofficial/sqlweb  :
For webbrowsers Not wasm now, a work-in-progress library? trying to use the best of any available sql engine in the browser. Translates any syntax if necessary. This 
all is to be used with this in mind that in some cases automatically websql (sqlite3) will be used, yeah websql that is about to be abandoned but now is available in maybe like 95% of browsers, if there is no websql available, it automatically switches of to sqlweb github plugin or manually you can choose sqlweb or websql. Basically sqlite3 syntax can be used (still much work to do left) and it is translated to sqlweb dialect which happily is compatible in some aspects with websql/sqlite3. Some misinformation from me may come from not knowing fully the topic by me :) . I also did some failed attempt to use duckdb WASM sqlite. It is not neccessary at the moment (as far as i know wasm is still not as fast as you would like it to be) to load such libraries. But i have in mind of using WASM libraries in the future.

<script src="scripts/jsstore.js "></script>
<script src="scripts/sqlweb.js"></script>

Some information for me. I mean it may not be usable for users of this solution:

  ///READ IT!!! READ IT!!!READ IT!!!READ IT!!!
  ///READ IT!!! READ IT!!!READ IT!!!READ IT!!!
  ///MUCH OF THE CODE BELOW TRANSLATING SQLITE INTO SQLWEB (GITHUB, BASED ON ISSTORE GITHUB)
  ///INITIALLY IT WAS TO AUTOMATICALLY CREATE DATABASE WITH TABLES AND INITIAL DATA
  ///BUT THE REST OF THE QUERIES DONE BY HAND - SELECT, UPDATE, DELETE, WHERE CLAUSE, ETC.
  ///it was to be used by dart/flutter web app connecting to native js
  ///AND WHAT'S IMPORTANT WHEN WEBSQL (CHROME BASED BROWSERS HAVE IT) IS NOT AVAILABLE
  ///THEN SQLWEB WORKAROUND WAS TO BE USED, THE DEVELOPMENT PROBABLY STOPPED

  ///READ IT!!! READ IT!!!READ IT!!!READ IT!!!
  ///READ IT!!! R EAD IT!!!READ IT!!!READ IT!!!
  /// there is php script adminer which manages and !EXPORTS! all the db  into sql (sqlite3), to recreate the db anywhere else from scratch
  /// the code below imports it translating into sqlweb github library dialect (esp. create table)
  ///but for crud operations:
  ///you can only use column names without single quotes (') for now in sqlite
  ///only "insert into" needed hard regexing
  ///select can be only used with "select *" - ONE STATEMENT
  ///update, delete, where seem to be much compatible - don't need regex to translate a query
  ///for non crud operations:
  ///much more seems to hace chance be compatible - you need to compare sqlweb with sqlite
  ///you possibly can have a chance for JOIN but for crud it is not necessary
  ///??? END OF READING

