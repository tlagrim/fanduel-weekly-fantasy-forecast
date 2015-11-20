<?php
include_once('simple_html_dom.php');


/* http://www.cs.stedwards.edu/~tlagrim/htvo/pullTesting/fdcrawl.php */


/* j is the year : 2011 - 2014 */
/* i is the week : week 1 - 17 */

for ($j = 11; $j <=14; $j++) {
	for ($i = 1; $i <=17; $i++) {
    	    $target_url = "http://rotoguru1.com/cgi-bin/fyday.pl?week={$i}&year=20{$j}&game=fd&scsv=1";
	    $html = new simple_html_dom();
	    $html->load_file($target_url);

    	    echo $target_url."...";

    	    /* write values into their own files */
    	    $filename = "fanduel20{$j}week{$i}.csv";
            foreach($html->find('pre') as $content) {
		$input = $content;
	    }
	    $text = substr($input, 5, -6);
	    $newfile = fopen($filename, "w") or die("Unable to open file!");
	    fwrite($newfile, $text);
	    fclose($newfile); 
	    echo "Done!";
    	}
}

/* Current year stats */
for ($k = 1; $k <= 6; $k++) {
    $current_target_url = "http://rotoguru1.com/cgi-bin/fyday.pl?week={$k}&game=fd&scsv=1";
    $html = new simple_html_dom();
    $html->load_file($current_target_url);

    echo $current_target_url."...";

    /* write values into their own files */
    $filename2 = "fanduel2015week{$k}.csv";
    foreach($html->find('pre') as $content2) {
        $input1 = $content2;
    }
    $input2 = substr($input1, 5, -6);
    $newfile2 = fopen($filename2, "w") or die("Unable to open file!");
    fwrite($newfile2, $input2);
    fclose($newfile2);
    echo "Done!<br>";
}

?>