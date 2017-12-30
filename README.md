<html>
<head>
<script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  </script>
  <script>    
    
    function swapImages(){
      var $active = $('#myGallery .active');
      var $next = ($('#myGallery .active').next().length > 0) ? $('#myGallery .active').next() : $('#myGallery img:first');
      $next.fadeIn(function(){         
        $active.removeClass('active');
        $next.addClass('active');
        $active.fadeOut();
      })
            
    }
    $(document).ready(function(){
      
      var height = $( window ).height();
      var width = $( window ).width();
      var size = width + ',' + height;
      
      var locations = [        
        {"src": "https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012,2013"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012,2013,2014"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012,2013,2014,2015"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012,2013,2014,2015,2016"}
        {"src":"https://public.tableau.com/profile/justin.seppi#!/vizhome/ReachOutandReadProgramMap/Dashboard1?:embed=yes&:toolbar=no&:format=png&:size=%22%20size%20%22&YEAR(Join%20Date)=2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017"}

        {"src": ""},
        
                ]
            
      $("#myGallery").attr('width',width);
      $("#myGallery").attr('height',height);
      
      var img = '';
      
      locations.forEach(function(element, index, array){
        
        
        if(index==0){         
          img = '<img src="'+locations[index].src+'" class="active" />';
        } else {
          img = '<img src="'+locations[index].src+'" />';         
        }
        console.log('index: '+index+' == '+img);    
        
        $(img).appendTo("#myGallery");
        
      })
      
      
      // Change 3000 to whatever time interval you prefer
      setInterval('swapImages()', 3000);
    });
  </script>
  <style>
    
    body {
      background-color: #353535;
    }
    #myGallery{
      position:relative;
    }
    #myGallery img{
      display:none;
      position:absolute;
      top:0;
      left:0;
    }
    #myGallery img.active{
      display:block;
    }
  </style>
</head>
<body>
  <div id="myGallery">
  </div>
</body>
</html>
